## Plotting Copy Number Results

**Module Author:** Candace Savonen ([@cansavvy](https://www.github.com/cansavvy))

This module plots genome-wide visualizations relating to copy number results.

### Creating the GISTIC plot

The GISTIC chromosomal plots can be re-generated by running this notebook:

```
Rscript -e "rmarkdown::render('analyses/cnv-chrom-plot/gistic_plot.Rmd', clean = TRUE)"
```

### Creating the CN status heatmap plot

The CN status heatmap can be re-generated by running this notebook:

```
Rscript -e "rmarkdown::render('analyses/cnv-chrom-plot/cn_status_heatmap.Rmd', clean = TRUE)"
```

### Output

The output of these notebooks is a series of plots:
- barplot of the GISTIC scores (`plots/gistic_plot.png`)
- line plots of the `seg.mean` by each histology group (e.g. `plots/Chondrosarcoma_plot.png`)
- heatmap of CN status by genome bin: (`plots/cn_status_heatmap.pdf`)

### Custom functions:
`bp_per_bin` - Given a binned genome ranges object and another `GenomicRanges` object, return the number of base pairs covered per bin. 
Can be used with any `GenomicRanges` object, but in this context is used within `call_bin_status` to find the number of base pairs of each CN status per bin.   
`call_bin_status` - Given a sample_id, copy number segment ranges, and binned genome ranges object, make a call for each bin on what CN copy status has the most coverage in the bin.
