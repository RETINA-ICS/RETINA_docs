# Walkthrough running a model

## Initializing a run

## Via a web browser

If you just want to test that the workflow is working  - but you can't change inputs because you don't have access to the app interface or the code

You can paste the following link in any (?) web browser

Version 1.1 (this will change if David updates the code)

[retina.hutton.ac.uk/retinaApp_activity_RunModel_Android_v1_1.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA&toid=osgb1000000175422042](https://retina.hutton.ac.uk/retinaApp_activity_RunModel_Android_v1_1.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA&toid=osgb1000000175422042)

the pieces of this link:
- the domain: retina.hutton.ac.uk
- the php script retina `App_activity_RunModel_Android_v1_1.php` which can be found in `\mnt\shared\projects\joint\202012_RETINA\retina.hutton.ac.uk\html`
	- all the php scripts for the app are in this directory and very well documented - they are all written by David D. please ask before making any changes. 
- toid = osgb1000000175422042
	- the site identifier: in this case, this is a site we have set up for testing model runs that is next to Balruddery. We call it TOID2
- DON'T TEST WITH TOIDS WE HAVEN'T SET UP YET
	- This starts a process that hangs (and we can't seem to kill) and we will need to restart the docker. 

Once you click the link, you will get a message that you have a run ID:

"Your activity has been recorded in the RETINA project database. A model has been run with Run ID: #####"

This number is the RETINA RUN ID
- Every time a request for a model run (or series of model runs) is sent from the app, it gets a retina run id. 
- If and only if this request is successful, the id is logged in the retina database

This is different than the PECAN run ID
- Every time a model is run, it is given a run id through PEcAn. 
- Even if the model is not successful, it will still be recorded in the BETY database. 

One RETINA RUN ID can be associated with many PECAN RUN ids

But you can get both of these from the log files in `\\narnia.cropdiversity.ac.uk\shared\projects\joint\202012_RETINA\retina.hutton.ac.uk\html\logs`

- `rscript_results_log_DATE` 
- `rscript_error_log_DATE` 

The log files also point to model output directories :
`/mnt/shared/projects/joint/202012_RETINA/pecan/volumes/pecan/pecan/workflows/PECAN_PECANID`

## Visualizations for app:
`\mnt\shared\projects\joint\202012_RETINA\pecan\volumes\pecan\pecan\dbfiles\input_app\html`

The folder name is determined by the RETINA run id and a randomly generated id for security 

## More about outputs 

All model output is stored in the directory 
`/mnt/shared/projects/joint/202012_RETINA/pecan/volumes/pecan/pecan/workflows` in the directory associated with its bety database workflow id. This can be found in the retina database and is associated with the retina run id. 

Look at the retina run table:
- If the run completed, the run will have a "finished at" date and a record for "out folder" this folder contians the output visulaizations, not the data itself however. 
- To see the actual data, use the retina_run_id to find the bety workflow_id in the  pecan_model_runs table. Again, if the run didn't complete, this record won't exist. 
- Then either use this workflow id to determine the path manually
	- For example:
		- retina_run_id 198 
		- workflow_id: 99000001015 
		- output directory: `/mnt/shared/projects/joint/202012_RETINA/pecan/volumes/pecan/pecan/workflows/PEcAn_99000001015`

- Alternatively, query the bety database for this path. It is the folder field in the workflows table. You could even do a joint query. Something along the lines of this if you queried from both databases:
```
SELECT w.folder 
	FROM workflows w 
	LEFT JOIN pecan_model_runs p
	WHERE w.id = p.workflow_id
```

	
Following this example of workflow 99000001015, inside this directory there is an out folder and then another layer of subdirectories. This is because the system has the potential to do ensemble runs. Then there would be multiple directories, each containing the output from a unique model run. As we are not running ensembles right now, there is only one sub directory. 

  `PEcAn_99000001015/out/99000000889/`

This is where you will find the output of the run, for a single model and site. The output is separated in to annual files and is in netcdf format. 

### Server Side Scripts

Coming soon 

setupPECAN.R

submitPECAN.R

### Retina side scripts

Coming soon

