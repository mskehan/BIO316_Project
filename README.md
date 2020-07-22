# BIO316_Project

library(ggplot2)
library(dplyr)
library(tidyr)
library(plyr)
library(sapply)

install.packages(sapply)
setwd("~/Desktop/Stonehill/Summer 2020/Project")
hospital_data=read.csv("Hospital_Readmissions_Reduction_Program.csv", na.strings=c('N/A', "Too Few to Report"))
head(hospital_data)
summary(hospital_data)

#Discharge vs Readmission
ggplot(data = hospital_data, mapping = aes(x= Number_of_Discharges, y = Number_of_Readmissions)) +
  geom_point(alpha = 0.2, size=2, color="blue") +
  ggtitle("Discharges vs Readmissions") +
  labs(x="Discharges", y="Readmissions") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6))

#Discharge vs Readmission by State
ggplot(data = hospital_data, mapping = aes(x= Number_of_Discharges, y = Number_of_Readmissions)) +
  geom_point(alpha = 0.2, size=2, color="blue") +
  ggtitle("Discharges vs Readmissions") +
  labs(x="Discharges", y="Readmissions") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6))+
  facet_wrap(~State)

#Discharge vs Readmission by Measure
ggplot(data = hospital_data, mapping = aes(x= Number_of_Discharges, y = Number_of_Readmissions)) +
  geom_point(alpha = 0.2, size=2, color="blue") +
  ggtitle("Discharges vs Readmissions") +
  labs(x="Discharges", y="Readmissions") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6))+
  facet_wrap(~Measure_Name)

#Expected Readmission Rate vs Predicted Readmission Rate
ggplot(data = hospital_data, mapping = aes(x= Expected_Readmission_Rate, y = Predicted_Readmission_Rate)) +
  geom_point(alpha = 0.2, size=2, color="blue") +
  ggtitle("Expected Readmission Rate vs Predicted Readmission Rate") +
  labs(x="Expected Readmission Rate", y="Predicted Readmission Rate") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6))

#Expected Readmission Rate vs Predicted Readmission Rate by State
ggplot(data = hospital_data, mapping = aes(x= Expected_Readmission_Rate, y = Predicted_Readmission_Rate)) +
  geom_point(alpha = 0.2, size=2, color="blue") +
  ggtitle("Expected Readmission Rate vs Predicted Readmission Rate") +
  labs(x="Expected Readmission Rate", y="Predicted Readmission Rate") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6))+
  facet_wrap(~State)

#Expected Readmission Rate vs Predicted Readmission Rate by Measure
ggplot(data = hospital_data, mapping = aes(x= Expected_Readmission_Rate, y = Predicted_Readmission_Rate)) +
  geom_point(alpha = 0.2, size=2, color="blue") +
  ggtitle("Expected Readmission vs Predicted Readmission") +
  labs(x="Expected Readmission", y="Predicted Readmission") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6))+
  facet_wrap(~Measure_Name)

#Excess Readmission Ratio by State
ggplot(data = hospital_data, mapping = aes(x=Excess_Readmission_Ratio )) +
  geom_histogram(color="blue") +
  ggtitle("Excess Readmission Ratio by State") +
  labs(x="Excess Readmission Ratio") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6)) +
  facet_wrap(~State)

#Excess Readmission Ratio by Measure
ggplot(data = hospital_data, mapping = aes(x=Excess_Readmission_Ratio )) +
  geom_histogram(color="blue") +
  ggtitle("Excess Readmission Ratio by State") +
  labs(x="Excess Readmission Ratio") +
  theme(axis.text.x = element_text(size=6)) +
  theme(axis.text.y = element_text(size=6)) +
  facet_wrap(~Measure_Name)
