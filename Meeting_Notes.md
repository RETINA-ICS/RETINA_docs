- Home of the project 
- /mnt/shared/projects/joint/202012_RETINA/pecan/
- `cd` to go to a new directory
- crtl + l clear the screen 
	- Tip: record a new macro and to use it crtl + space

- Main directory where work lives (scripts, data, etc) 
`/mnt/shared/projects/joint/202012_RETINA/pecan/volumes/pecan/pecan`  

- workflows
- test_API
- dbfiles
- RETINA
- test_plots

- Inside rstudio on docker
-`/mnt/shared/projects/joint/202012_RETINA/pecan/volumes/pecan/pecan` shortened to `/data`

Portforwarding from Iain:

ssh -L 8000:localhost:8000 -J ecowdery@gruffalo.cropdiversity.ac.uk ecowdery@retina
ssh -L 8000:retina:8000 ejones@gruffalo.cropdiversity.ac.uk


ssh -L 8000:localhost:8000 -J ejones@gruffalo.cropdiversity.ac.uk ejones@retina

