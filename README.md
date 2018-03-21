# Zhu-Lab
## Daily data to Monthly Variance
La_BSA_sho <- read.csv("G:/Team Drives/Urban Albedo/Data/Albedo/CSV_Filtered/Los Angeles_BSA_sho.csv")
short.date = strftime(La_BSA_sho$Date, "%Y-%m")
aggr.stat = aggregate(La_BSA_sho$Value ~ short.date, FUN = var)
write.csv(aggr.stat, "La_BSA_sho.csv")

La_BSA_vis <- read.csv("G:/Team Drives/Urban Albedo/Data/Albedo/CSV_Filtered/Los Angeles_BSA_vis.csv")
short.date = strftime(La_BSA_vis$Date, "%Y-%m")
aggr.stat = aggregate(La_BSA_vis$Value ~ short.date, FUN = var)
write.csv(aggr.stat, "La_BSA_vis.csv")

La_WSA_nir <- read.csv("G:/Team Drives/Urban Albedo/Data/Albedo/CSV_Filtered/Los Angeles_WSA_nir.csv")
short.date = strftime(La_WSA_nir$Date, "%Y-%m")
aggr.stat = aggregate(La_WSA_nir$Value ~ short.date, FUN = var)
write.csv(aggr.stat, "La_WSA_nir.csv")

La_WSA_sho <- read.csv("G:/Team Drives/Urban Albedo/Data/Albedo/CSV_Filtered/Los Angeles_WSA_sho.csv")
short.date = strftime(La_WSA_sho$Date, "%Y-%m")
aggr.stat = aggregate(La_WSA_sho$Value ~ short.date, FUN = var)
write.csv(aggr.stat, "La_WSA_sho.csv")

La_WSA_vis <- read.csv("G:/Team Drives/Urban Albedo/Data/Albedo/CSV_Filtered/Los Angeles_WSA_vis.csv")
short.date = strftime(La_WSA_vis$Date, "%Y-%m")
aggr.stat = aggregate(La_WSA_vis$Value ~ short.date, FUN = var)
write.csv(aggr.stat, "La_WSA_vis.csv")



## Open individual files seperately 

BSA_sho <- read.csv("C:/Users/xbear/Documents/1/La_BSA_sho.csv")
BSA_vis <- read.csv("C:/Users/xbear/Documents/1/La_BSA_vis.csv")
WSA_nir <- read.csv("C:/Users/xbear/Documents/1/La_WSA_nir.csv")
WSA_sho <- read.csv("C:/Users/xbear/Documents/1/La_WSA_sho.csv")
WSA_vis <- read.csv("C:/Users/xbear/Documents/1/La_WSA_vis.csv")



#plots time series
library(ggplot2)

plot2 <-ggplot(BSA_sho, aes(x = X, La_BSA_sho.Value )) + geom_line() + geom_smooth(method = 'lm')
plot2 + ggtitle("BSA_sho_Var") 
ggsave("BSA_sho_Var.png")


plot3 <-ggplot(BSA_vis, aes(x = X, La_BSA_vis.Value )) + geom_line() + geom_smooth(method = 'lm')
plot3 + ggtitle("BSA_vis_Var") 
ggsave("BSA_vis_Var.png")

plot4 <-ggplot(WSA_nir, aes(x = X, La_WSA_nir.Value )) + geom_line() + geom_smooth(method = 'lm')
plot4 + ggtitle("WSA_nir_Var") 
ggsave("WSA_nir_Var.png")

plot5 <-ggplot(WSA_sho, aes(x = X, La_WSA_sho.Value )) + geom_line() + geom_smooth(method = 'lm')
plot5 + ggtitle("WSA_sho_Var") 
ggsave("WSA_sho_Var.png")

plot6 <-ggplot(WSA_vis, aes(x = X, La_WSA_vis.Value )) + geom_line() + geom_smooth(method = 'lm')
plot6 + ggtitle("WSA_vis_Var") 
ggsave("WSA_vis_Var.png")

