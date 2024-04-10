
# Running the model 

## Server Side Scripts

setupPECAN.R

submitPECAN.R

## Retina side scripts

# Outputs 

All model output is stored in the directory 
`/mnt/shared/projects/joint/202012_RETINA/pecan/volumes/pecan/pecan/workflows` in the directory associated with its bety database workflow id. This can be found in the retina database and is associatedwith the retina run id. 

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
