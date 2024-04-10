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
