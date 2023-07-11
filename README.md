# Combined Cycle Power Plant (CCPP)

![alt tag](https://github.com/Abdelrahman898/e2e_ds_projec/blob/main/images/burullus-260917-dji-0026-2.jpg)

Power prediction is important not only for the smooth and economic operation of a combined cycle power plant (CCPP) but also to avoid technical issues such as power outages. In this work, we propose to utilize machine learning algorithms to predict the hourly-based electrical power generated by a CCPP. For this, the generated power is considered a function of four fundamental parameters which are relative humidity, atmospheric pressure, ambient temperature, and exhaust vacuum. The measurements of these parameters and their yielded output power are used to train and test the machine learning models. The dataset for the proposed research is gathered over a period of six years and taken from a standard and publicly available machine learning repository.

We predicting the net hourly electrical energy output (PE) of the plant using [dataset](https://archive.ics.uci.edu/ml/datasets/Combined+Cycle+Power+Plant) from UCI Machine Learning Repository.

The accurate prediction of power generated by a plant helps in reducing various related issues such as power outages,economic, and technical difficulties. In particular, an inaccurate prediction results in the rise of per unit cost of electric power due to the high fuel consumption. Hence, in this work, we aim at achieving a precise prediction of electric power of a base load CCPP on full load conditions thus ensuring decreased cost of per unit of electric power.

We used Various probabilistic approaches for CCPP power prediction of electric power of CCPP operated on full load using DecisionTreeRegressor (DT), linear regression (LR), artificial neural network (ANN), RandomForestRegressor (RF), LGBMRegressor (LGBR), XGBRegressor (XGBR), CatBoostRegressor (CATBR), and SVM (SVR) are used to improve the power prediction. The individual and cumulative effects of each parameter are evaluated on output power prediction using these machine learning algorithms. These algorithms are compared to find the best results using optomization framework as GridSearchCV. The best performance among these machine learning models is analyzed by choosing the least RMSE and MAE values which is our metrics.

## Data Set Information

>The dataset contains 9568 data points collected from a Combined Cycle Power Plant over 6 years (2006-2011), when the power plant was set to work with full load. Features consist of hourly average ambient variables Ambient Temperature (AT), Ambient Pressure (AP), Relative Humidity (RH) and Exhaust Vacuum (V) to predict the net hourly electrical energy output (PE) of the plant. A combined cycle power plant (CCPP) is composed of gas turbines (GT), steam turbines (ST) and heat recovery steam generators. In a CCPP, the electricity is generated by gas and steam turbines, which are combined in one cycle, and is transferred from one turbine to another. While the Vacuum is colected from and has effect on the Steam Turbine, the other three of the ambient variables effect the GT performance.

## Attribute Information

Features consist of hourly average ambient variables :

- Temperature (T) in the range `1.81°C and 37.11°C`
- Ambient Pressure (AP) in the range `992.89-1033.30 milibar`
- Relative Humidity (RH) in the range `25.56% to 100.16%`
- Exhaust Vacuum (V) in teh range `25.36-81.56 cm Hg`
- Net hourly electrical energy output (EP) `420.26-495.76 MW`

The averages are taken from various sensors located around the plant that record the ambient variables every second. The variables are given without normalization

![alt tag](https://github.com/Abdelrahman898/e2e_ds_projec/blob/main/images/output1.png)

## Abstract

The dataset contains 9568 data points collected from a Combined Cycle Power Plant over 6 years (2006-2011), when the plant was set to work with full load.

| Q: | A | Q: | A | Q: | A | 
| :---: | :---: | :---: | :---: | :---: | :---: |
| **Data Set Characteristics:** | Multivariate | **Number of Instances:** | 9568 | **Area:** | computer |
| **Attribute Characteristics:** | Real | **Number of Attributes:** | 4 | **Date Donated:** | 2014-03-26 |
| **Associated Tasks:** | Regression | **Missing Values?:** | N/A |

## Source

Pınar Tüfekci, Çorlu Faculty of Engineering, Namık Kemal University, TR-59860 Çorlu, Tekirdağ, Turkey
Email: ptufekci @ nku.edu.tr

Heysem Kaya, Department of Computer Engineering, Boğaziçi University, TR-34342, Beşiktaş, İstanbul, Turkey
Email: heysem @ boun.edu.tr

## Create virtual environment

Using vscode with `cmd` to create a virtual environment with the following command:

> Creating virtual environment

```bash
python -m venv .venv 
```

Which python mean the `python.exe` location in your PC.

> Activating virtual environment

```bash
.venv/Scripts/activate 
```

> Installing requirements

```bash
pip install -r requirements.txt 
```

## Data description

```python
>>> df.head()
	AT	V	AP	RH	PE
0	14.96	41.76	1024.07	73.17	463.26
1	25.18	62.96	1020.04	59.08	444.37
2	5.11	39.4	1012.16	92.14	488.56
3	20.86	57.32	1010.24	76.64	446.48
4	10.82	37.5	1009.23	96.62	473.9
```

```python
>>> df.info()
#   Column  Non-Null Count  Dtype 
---  ------  --------------  ----- 
 0   AT      47844 non-null  float(64)
 1   V       47844 non-null  float(64)
 2   AP      47844 non-null  float(64)
 3   RH      47844 non-null  float(64)
 4   PE      47844 non-null  float(64)
dtypes: float(5)
```

```python
>>> df.describe()
---------------------------------------------------------------------------------------
    count       mean       std       min       25%        50%       75%          max 
---------------------------------------------------------------------------------------
AT  47840.0  19.651231   7.452162    1.81    13.5100     20.345     25.72       37.11

V   47840.0  54.305804   12.707362   25.36   41.7400     52.080     66.54       81.56

AP  47840.0  1013.259078 5.938535    992.89  1009.1000   1012.940   1017.26     1033.30

RH  47840.0  73.308978   14.599658   25.56   63.3275     74.975     84.83       100.16

PE  47840.0  454.365009  17.066281   420.26  439.7500    451.550    468.43      495.76

```

## Proposed architecture of the prediction of CCPP power using ML algorithm

![alt tag](https://github.com/Abdelrahman898/e2e_ds_projec/blob/main/images/Screenshot%202023-07-02%20224545.png)

## Regression Supervised ML

Regression is a popular branch of supervised machine learning that focuses on predicting continuous numerical values based on input data. In regression, the goal is to build a model that can learn the underlying relationship between input
features and the target variable, enabling accurate predictions on new, unseen data.

![alt tag](https://github.com/Abdelrahman898/e2e_ds_projec/blob/main/images/output.png)

## Result 

**XGBRegressor** has the least RMSE.

![alt tag](https://github.com/Abdelrahman898/e2e_ds_projec/blob/main/images/newplot2.png)
