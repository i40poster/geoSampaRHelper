# Overview
The goal of this project is to provide a helper lib to handle Sao Paulo/SP/Brazil Geo Data

# geoSampaRHelper

# Observation

This lib will work best if you use in a RStudio custom install that is  described at [i40poster/geoFracker](https://github.com/i40poster/geoFracker).

# Use

```R
# R Commands:
## 1. install
install.packages("devtools")
library(devtools)
devtools::install_github("i40poster/geoSampaRHelper")

## 2 .Sample of use:
library(helper4geosampa)

Abastecimento = downloadAndUnzipShp("http://geosampa.prefeitura.sp.gov.br/PaginasPublicas/downloadArquivoOL.aspx?orig=DownloadCamadas&arq=03_Equipamentos%5C%5CAbastecimento%5C%5CShapefile%5C%5CEQUIPAMENTOS_SHP_TEMA_ABASTECIMENTO&arqTipo=Shapefile")

http://geosampa.prefeitura.sp.gov.br/PaginasPublicas/downloadArquivoOL.aspx?orig=DownloadCamadas&arq=03_Equipamentos%5C%5CAbastecimento%5C%5CShapefile%5C%5Cequipamento_abastecimento&arqTipo=Shapefile
http://geosampa.prefeitura.sp.gov.br/PaginasPublicas/downloadArquivoOL.aspx?orig=DownloadCamadas&arq=03_Equipamentos%5C%5CAbastecimento%5C%5CShapefile%5C%5CEQUIPAMENTOS_SHP_TEMA_ABASTECIMENTO&arqTipo=Shapefile

## 3. Working with Data:
### Loading layer of data:
Abastecimento1 <- readOGR(dsn=Abastecimento$dir[1], layer=Abastecimento$shapeclass[1])
Abastecimento2 <- readOGR(dsn=Abastecimento$dir[1], layer=Abastecimento$shapeclass[2])
Abastecimento3 <- readOGR(dsn=Abastecimento$dir[1], layer=Abastecimento$shapeclass[3])
Abastecimento4 <- readOGR(dsn=Abastecimento$dir[1], layer=Abastecimento$shapeclass[4])
Abastecimento5 <- readOGR(dsn=Abastecimento$dir[1], layer=Abastecimento$shapeclass[5])
Abastecimento6 <- readOGR(dsn=Abastecimento$dir[1], layer=Abastecimento$shapeclass[6])

## 1,2,3 seems to have the same data of 4,5,6
## Data from the source are provided in to formats,
## creating replication if you merge all the content.

AbastecimentoFinal <- rbind(Abastecimento1,Abastecimento2,Abastecimento3)


```

# Reference

Data source: [Digital Map of the City of São Paulo](http://geosampa.prefeitura.sp.gov.br/PaginasPublicas/_SBC.aspx)

Created based on: [Source](https://hilaryparker.com/2014/04/29/writing-an-r-package-from-scratch/)
