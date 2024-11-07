# Restarting Docker

If changes are made to any RETINA functions (ie plotting) docker needs to be restarted

go to the docker container

`cd /mnt/shared/projects/joint/202012_RETINA/pecan/docker/`

`docker compose down`

`docker compose up -d`

Pick a TOID like osgb1000000175422042

Then try a new run:

Version 1_1

[retina.hutton.ac.uk/retinaApp_activity_RunModel_Android_v1_1.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA&toid=osgb1000000175422042](https://retina.hutton.ac.uk/retinaApp_activity_RunModel_Android_v1_1.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA&toid=osgb1000000175422042)

Version 1_0

```bash
<https://retina.hutton.ac.uk/retinaApp_activity_RunModel_Android_v1_0.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA&toid=osgb1000000175422042>
```

# Logs and Errors

Look at logs and errors

`cd /mnt/shared/projects/joint/202012_RETINA/retina.hutton.ac.uk/html/logs`

`watch less rscript_error_log.txt`

`watch less rscript_results_log.txt`

```bash
<https://retina.hutton.ac.uk/retinaApp_activity_RunModel_Android_v1_1.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA&toid=osgb1000002019663779>
```

[retinaApp_activity_RunModel_Android_v1_1.php](https://retina.hutton.ac.uk/
retinaApp_activity_RunModel_Android_v1_1.php?getKey=CQHXu2H4S31dXt9VqWXd&userName=retinaTesting@hutton.ac.uk&userPass=kjasdf83AJNCTO039AA)
\&
toid=osgb1000002019663779

# Rebuilding pecan API

If you ever make changes to any of the pecan API functions, 
rebuilding pecan and bringing docker down and up won't be enough
for those changes to show.

You need to rebuild the pecan API docker. 


Steps:

After logging in to gruffalo and retina, 

go to the docker directory

`cd /mnt/shared/projects/joint/202012_RETINA/pecan/docker/`

always check to make sure that you're in the right docker folder 
with something like `docker compose ps` which will list
all the running containers. 
If they don't look familiar, you're in the wrong place and you're about
to shut down the wrong docker. Turn back!

When you're ready, bring docker down

`docker compose down`

Then MOVE TO A NEW DOCKER DIRECTORY: the pecan api docker directory

this is where you will rebuild the API docker

`cd apps/api`

`docker build -t pecan/api:develop .`

When this has completed MOVE DIRECTORIES AGAIN
back to the pecan docker directory

either with `cd ../..`
or write out the full path again
`cd /mnt/shared/projects/joint/202012_RETINA/pecan/docker/`

Bring docker up

`docker compose up -d`

Give it a minute for everything to start. 
But you might need bring docker up twice because API has some trouble starting. 


List all the running containers

`docker compose ps` 

and check to see that `pecan/api:develop` is up and running and
that it has just been updated!
