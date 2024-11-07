# Meeting Notes

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



ssh -L 8000:localhost:8000 -J ejones@gruffalo.cropdiversity.ac.uk ejones@retina




ssh -L 8000:retina:8000 ejones@gruffalo.cropdiversity.ac.uk

Notes from 23/5/24

- Check out samba 
-  Once you have samba just paste this:
	- DNDC code is in `\\narnia.cropdiversity.ac.uk\shared\projects\joint\202012_RETINA\pecan\docker\models\dndc`
- Check out the RETINA code
	- `\\narnia.cropdiversity.ac.uk\shared\projects\joint\202012_RETINA\pecan\volumes\pecan\pecan\RETINA`
		- plot_wf_RETINA_func
		- 


#  Plotting Visualizations


Pull plot_data.rds from the workflow directory to anywhere you want to use R

```
library(tidyverse)

test_model_output <- readRDS("lot_data.rds")

ggplot(test_model_output) + 
  geom_line(aes(x = posix, y = value,
                group = group_plot,
                color = group_color)) +
  facet_grid(rows = vars(var), cols = vars(site), scales = "free") +
  ggtitle(paste(Sys.time()))+
  theme(legend.position="bottom") +
  scale_color_viridis_d(direction = -1) +
  theme_classic()


test_model_output_wide <- pivot_wider(test_model_output,
  names_from = var, values_from = value
  )


```