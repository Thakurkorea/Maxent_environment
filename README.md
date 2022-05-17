# Maxent_environment
Maxent_tif_to_grd
# lets' change the file to .grd format
fl_name<-"Maxent_pred"    # output data folder
in_path<-'E:/MAxent for invassive (생태원)/wc2.1_10m_bio_evl/'  # data folder
out_path<-paste(in_path,fl_name,collapse = NULL) # output folder name
dir.create(out_path)    # make new directory folder
filenames <- list.files(path = file.path(in_path), pattern="*.tif")
length(filenames)   # check no of files in folder
for (lr in filenames)
{print(lr)
r_tif<- raster(file.path(in_path,lr))
writeRaster(r_tif,filename = file.path(out_path,lr),format= 'raster',overwrite=TRUE)
}


https://www.rdocumentation.org/packages/raster/versions/3.5-15/topics/writeFormats
