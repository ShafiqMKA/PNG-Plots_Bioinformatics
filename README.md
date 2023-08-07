# Bioinformatics
Create mutation PLOT using GGPLOT and save it as high resolution PNG:
#Load the following Libraries:
library(tidyr)
library(stats)
library(ggplot2)
library(dplyr)
library(graphics)
library(tidyverse)

#Now excess your CSV file and save it inside a vecter
dtt1 <- read.csv(file.choose())
#view youre file to check which value you assign to the x and y coordinates 
#as we save our plot as png so we set the working directory 
setwd("copypaste your desired directory here")
#set your png parameter here like file name hight, resolution etc. 
png(ggplot(), file="final_mutation.png", height = 6, width = 6, units = "in", res = 800)
#create your ggplot
#ddt1 where your file is store, aes assign values on the x and y coordinates 
ggplot(dtt1, aes(x= Type, y= mRNA.Expression, label= Mutations))+
#geom point will mention each sample with mutation
  geom_point(size=6, col=c("red"))+geom_text(hjust=0,vjust=0)+
#labs will allow to alter the coordinates names, and title 
  labs(x= "Mutation", y= "mRNA Expression", title = "B")+
#theme will all the position of the legend, background and so on 
  theme(legend.position = "top", plot.title = element_text(hjust = 0.5, face= "bold"))
  dev.off()
