# The-Python-Pandas-Tutorial

https://www.youtube.com/watch?v=LJTm8_IJGNY 

https://raw.githubusercontent.com/RodrigoMvs123/The-Python-Pandas-Tutorial/main/README.md

https://github.com/RodrigoMvs123/The-Python-Pandas-Tutorial/blame/main/README.md

https://pandas.pydata.org/
Pandas
Is a software library written for the python programming language for data manipulation and analysis 
https://jupyter.org/install
https://jupyter.org/try-jupyter/lab/?path=notebooks%2FIntro.ipynb 

Intro to Pandas and Series

In: import numpy as np 
In: sales = [1402, 548, 1122]
In: sales
Out: [1402, 548, 1122]
In: sales_arr = np.array(sales)
In: sales_arr
Out: array([1402,  548, 1122])
In: sales_arr[1]
Out: 548
In: import pandas as pd
In: sales_series = pd.Series(sales_arr)
In: sales_series
Out: 
0    1402
1     548
2    1122
dtype: int32
In: sales_series[1]
Out: 548
In: names = ["Ellie", "Tom", "Mike"]
In: sales_series = pd.Series(sales_arr, names)
In: sales_series
Out: 
Ellie    1402
Tom       548
Mike     1122
dtype: int32
In: sales_series ["Tom"]
Out: 548
In: sales_series = [1]
Out: 548
In: sales = {"Ellie":1402, "Tom": 548, "Mike": 1122}
In: pd.Series(sales)
Out: 
Ellie    1402
Tom       548
Mike     1122
dtype: int64

Series Operations 

In: sales_series
Out: 
Ellie    1402
Tom       548
Mike     1122
dtype: int64
In: sales_series * 0.7
Out:
Ellie    981.4 
Tom    386.3 
Mike    785.4
dtype: float64
In: april_sales = {c, "Tom": 548, "Mike": 1122}
In: may_sales = {"Ellie": 704, "Tom": 433, "Ted": 255}
In: april_Sales = pd.Series(april_sales)
In: may_Sales =pd.Series(may_sales)
In: april_Sales
Out:
Ellie    1402
Tom       548
Mike     1122
dtype: int64
In: may_Sales
Out: 
Ellie    704
Tom      433
Ted      255
dtype: int64
In: april_Sales + may_Sales
Out: 
Ellie    2106.0
Mike        NaN
Ted         NaN
Tom       981.0
dtype: float64
In: april_Sales.add(may_Sales)
Out:
Ellie    2106.0
Mike        NaN
Ted         NaN
Tom       981.0
dtype: float64
In: april_Sales.add(may_Sales, fill_value=0)
Out: 
Ellie    2106.0
Mike     1122.0
Ted       255.0
Tom       981.0
dtype: float64

Dataframes

In: sales = np.random.randint(200, 2001, (4, 3))
In: sales
Out:
array([[ 836, 1671,  288],
       [1534, 1477, 1385],
       [ 252, 1471, 1148],
       [ 581, 1775, 1447]])
In: names = ["Ellie", "Mike", "Ted", "Tom"]
In: months = ["April", "May", "June"]
In: df = pd.DataFrame(sales, index=names, columns=months)
In: df
Out:


April
May
June
Ellie
1686
1333
1498
Mike
820
426
1589
Ted
362
1691
1814
Tom
783
1215
1526

In: ls
NumPy/ Pandas/ Untitled.ipynb
In: ls Pandas
Padas copy.ipynb Pandas.ipynb data/
In: ls Pandas/data
Out: cars.csv
In: df = pd.read_csv('./Pandas/data/cars.csv')
In:df
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
car
type
year
price
finance
day
dealer
customer
social_security
sex


0
Mercedes-Benz A-Class
sedan
2019
39000
no
Sun
Mike
Stanley
555342396
M
1
Audi A6
sedan
2021
67800
yes
Mon
Sam
Brittany
887766234
F
2
Nissan Altima
sedan
2015
17500
no
Sun
Mike
Todd
998573477
M
3
Chevrolet Equinox
SUV
2013
9600
no
Wed
Turner
Jasime
342234563
F
4
Hyundai Accent
hatchback
2017
23000
yes
Thur
Maddy
Sam
570566354
M
5
Porsche Cayenne
coupe
2021
82000
yes
Fri
Mike
Morgan
968258639
F
6
Volkswagen Jetta
sedan
2000
3500
no
Tue
Turner
Aaron
557275923
M
7
Audi A6
sedan
2020
78444
no
Sat
Brittany
Shelby
223955366
F
8
Jeep Wrangler
SUV
2017
33553
yes
Fri
Mike
Sam
877425852
M
9
Volkswagen Jetta
sedan
2012
9855
no
Tue
Sam
Jessie
885354544
F
10
Hyundai Accent
hatchback
2014
17434
no
Mon
Maddy
Taylor
870566354
F
11
Hyundai Accent
hatchback
2011
7434
no
Wed
Maddy
Monte
870066354
M
12
Mercedes-Benz A-Class
hatchback
2015
25453
yes
Tue
Mike
Alyssa
579521683
F
13
Nissan Altima
sedan
2010
10983
no
Mon
Turner
Felix
994853335
M
14
Chevrolet Equinox
SUV
2016
23998
yes
Fri
Mike
Kyle
947577792
M
15
BMW M8
coupe
2021
158000
yes
Wed
Maddy
Nicole
338559922
F
16
Toyota 4Runner
SUV
2022
54000
no
Thur
Mike
Jan
462375343
F
17
Audi A6
sedan
2015
58444
yes
Sat
Brittany
Qatava
223855366
M
18
Jaguar XF
sedan
2019
57744
yes
Sun
Turner
Taylor
884352886
F
19
Volkswagen Jetta
sedan
2004
2235
no
Tue
Turner
Git
995358322
M
20
Honda Civic
sedan
2018
22333
no
Fri
Mike
Jon
334642443
M
21
BMW M8
coupe
2020
140553
no
Wed
Maddy
Sal
326234886
M
22
Ford Maverick
pickup
2018
27433
no
Mon
Sam
Murry
588845355
M
23
Jeep Wrangler
SUV
2021
43553
yes
Fri
Mike
Don
277425852
M
24
Audi A6
sedan
2021
78444
no
Thur
Brittany
Qatava
223855366
M
25
Genesis GV80
SUV
2021
80444
yes
Mon
Mike
Selena
994447745
F
26
Porsche Cayenne
coupe
2015
52000
no
Thur
Turner
Emily
958258639
F
27
Volkswagen Jetta
sedan
2014
25356
no
Wed
Sam
Pam
995538822
F
28
Maserati Levante
SUV
2020
104325
yes
Mon
Mike
Cam
452685274
M
29
Hyundai Accent
hatchback
2017
17434
no
Thurs
Maddy
Bob
70066354
M
30
Honda Civic
sedan
2000
2333
no
Sat
Brittany
Allen
134642443
M
31
Chevrolet Camaro
coupe
2018
76550
yes
Wed
Turner
Sarah
552422222
F
32
Maserati Levante
SUV
2020
134325
yes
Sun
Mike
Todd
952685274
M
33
Mercedes-Benz A-Class
sedan
2021
44032
yes
Mon
Turner
Jon
996435345
M
34
Ford Maverick
pickup
2013
36033
yes
Sun
Turner
Bailey
508845355
F
35
Jeep Wrangler
SUV
2021
43553
yes
Fri
Mike
Don
277425852
M
36
Porsche 911
coupe
2021
185543
yes
Mon
Sam
Cam
452685274
M
37
Hyundai Accent
hatchback
2015
13434
yes
Thurs
Brittany
Don
277425852
M
38
Hyundai Accent
hatchback
2015
13434
yes
Thurs
Brittany
Don
277425852
M
39
Cadillac Escalade
sedan
2017
85474
no
Tue
Mike
Harris
885437455
M
40
Genesis GV80
SUV
2020
78422
yes
Mon
Sam
Rachel
995943645
F
41
Jeep Wrangler
SUV
2002
3553
no
Sun
Brittany
Porsche
277425858
F
42
Genesis GV80
SUV
2020
77842
yes
Sat
Mike
Edward
885352535
M
43
Cadillac Escalade
sedan
2020
48422
yes
Mon
Sam
Rachel
995943645
F
44
Bentley Bentayga
SUV
2020
232000
no
Wed
Mike
Gabrielle
885353455
F

In: df.head()
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysex0Mercedes-Benz A-Classsedan201939000noSunMikeStanley555342396M1Audi A6sedan202167800yesMonSamBrittany887766234F2Nissan Altimasedan201517500noSunMikeTodd998573477M3Chevrolet EquinoxSUV20139600noWedTurnerJasime342234563F4Hyundai Accenthatchback201723000yesThurMaddySam570566354M

Conditional Selection 

In: df["year"]
Out:
0     2019
1     2021
2     2015
3     2013
4     2017
5     2021
6     2000
7     2020
8     2017
9     2012
10    2014
11    2011
12    2015
13    2010
14    2016
15    2021
16    2022
17    2015
18    2019
19    2004
20    2018
21    2020
22    2018
23    2021
24    2021
25    2021
26    2015
27    2014
28    2020
29    2017
30    2000
31    2018
32    2020
33    2021
34    2013
35    2021
36    2021
37    2015
38    2015
39    2017
40    2020
41    2002
42    2020
43    2020
44    2020
Name: year, dtype: int64
In: type(df[“year”])
Out: padas.core.series.Series
In: df[“year”] > 2015
Out:
0      True
1      True
2     False
3     False
4      True
5      True
6     False
7      True
8      True
9     False
10    False
11    False
12    False
13    False
14     True
15     True
16     True
17    False
18     True
19    False
20     True
21     True
22     True
23     True
24     True
25     True
26    False
27    False
28     True
29     True
30    False
31     True
32     True
33     True
34    False
35     True
36     True
37    False
38    False
39     True
40     True
41    False
42     True
43     True
44     True
Name: year, dtype: bool
In: bool_series = df[“year”] > 2015
In: df[bool_series]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysex1Audi A6sedan202167800yesMonSamBrittany887766234F5Porsche Cayennecoupe202182000yesFriMikeMorgan968258639F15BMW M8coupe2021158000yesWedMaddyNicole338559922F16Toyota 4RunnerSUV202254000noThurMikeJan462375343F23Jeep WranglerSUV202143553yesFriMikeDon277425852M24Audi A6sedan202178444noThurBrittanyQatava223855366M25Genesis GV80SUV202180444yesMonMikeSelena994447745F33Mercedes-Benz A-Classsedan202144032yesMonTurnerJon996435345M35Jeep WranglerSUV202143553yesFriMikeDon277425852M36Porsche 911coupe2021185543yesMonSamCam452685274M
In: df[df['year'] > 2020]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysex1Audi A6sedan202167800yesMonSamBrittany887766234F5Porsche Cayennecoupe202182000yesFriMikeMorgan968258639F15BMW M8coupe2021158000yesWedMaddyNicole338559922F16Toyota 4RunnerSUV202254000noThurMikeJan462375343F23Jeep WranglerSUV202143553yesFriMikeDon277425852M24Audi A6sedan202178444noThurBrittanyQatava223855366M25Genesis GV80SUV202180444yesMonMikeSelena994447745F33Mercedes-Benz A-Classsedan202144032yesMonTurnerJon996435345M35Jeep WranglerSUV202143553yesFriMikeDon277425852M36Porsche 911coupe2021185543yesMonSamCam452685274M
In: df[df[“finance”] == “yes”]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In: df[(df[“year”] >= 2020) & (df[“price”] .>= 100000)]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysex15BMW M8coupe2021158000yesWedMaddyNicole338559922F21BMW M8coupe2020140553noWedMaddySal326234886M28Maserati LevanteSUV2020104325yesMonMikeCam452685274M32Maserati LevanteSUV2020134325yesSunMikeTodd952685274M36Porsche 911coupe2021185543yesMonSamCam452685274M44Bentley BentaygaSUV2020232000noWedMikeGabrielle885353455F
In: df[(df[“year”] >= 2020) | (df[“price”] .>= 100000)]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In:df[(df["day"] == "Sat")] | df(df["day"] == "Sun")]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysex0Mercedes-Benz A-Classsedan201939000noSunMikeStanley555342396M2Nissan Altimasedan201517500noSunMikeTodd998573477M7Audi A6sedan202078444noSatBrittanyShelby223955366F17Audi A6sedan201558444yesSatBrittanyQatava223855366M18Jaguar XFsedan201957744yesSunTurnerTaylor884352886F30Honda Civicsedan20002333noSatBrittanyAllen134642443M32Maserati LevanteSUV2020134325yesSunMikeTodd952685274M34Ford Maverickpickup201336033yesSunTurnerBailey508845355F41Jeep WranglerSUV20023553noSunBrittanyPorsche277425858F42Genesis GV80SUV202077842yesSatMikeEdward885352535M
In: df[df[“day”].isin([“Mon”, “Tue”, “Wed”, “Thur”, “Fri”])]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysex1Audi A6sedan202167800yesMonSamBrittany887766234F3Chevrolet EquinoxSUV20139600noWedTurnerJasime342234563F4Hyundai Accenthatchback201723000yesThurMaddySam570566354M5Porsche Cayennecoupe202182000yesFriMikeMorgan968258639F6Volkswagen Jettasedan20003500noTueTurnerAaron557275923M8Jeep WranglerSUV201733553yesFriMikeSam877425852M9Volkswagen Jettasedan20129855noTueSamJessie885354544F10Hyundai Accenthatchback201417434noMonMaddyTaylor870566354F11Hyundai Accenthatchback20117434noWedMaddyMonte870066354M12Mercedes-Benz A-Classhatchback201525453yesTueMikeAlyssa579521683F13Nissan Altimasedan201010983noMonTurnerFelix994853335M14Chevrolet EquinoxSUV201623998yesFriMikeKyle947577792M15BMW M8coupe2021158000yesWedMaddyNicole338559922F16Toyota 4RunnerSUV202254000noThurMikeJan462375343F19Volkswagen Jettasedan20042235noTueTurnerGit995358322M20Honda Civicsedan201822333noFriMikeJon334642443M21BMW M8coupe2020140553noWedMaddySal326234886M22Ford Maverickpickup201827433noMonSamMurry588845355M23Jeep WranglerSUV202143553yesFriMikeDon277425852M24Audi A6sedan202178444noThurBrittanyQatava223855366M25Genesis GV80SUV202180444yesMonMikeSelena994447745F26Porsche Cayennecoupe201552000noThurTurnerEmily958258639F27Volkswagen Jettasedan201425356noWedSamPam995538822F28Maserati LevanteSUV2020104325yesMonMikeCam452685274M31Chevrolet Camarocoupe201876550yesWedTurnerSarah552422222F33Mercedes-Benz A-Classsedan202144032yesMonTurnerJon996435345M35Jeep WranglerSUV202143553yesFriMikeDon277425852M36Porsche 911coupe2021185543yesMonSamCam452685274M39Cadillac Escaladesedan201785474noTueMikeHarris885437455M40Genesis GV80SUV202078422yesMonSamRachel995943645F43Cadillac Escaladesedan202048422yesMonSamRachel995943645F44Bentley BentaygaSUV2020232000noWedMikeGabrielle885353455F


Pandas Methods


.apply()


In: def price_after_tax(price):
       return round(price * 1.13, 0)
In: tax_after_price(df[“price”][2])
Out: 19775.0
In: df[“total_price”] = df[“price”].apply(price_after_tax) 
In: df 
Out: 
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysexprice_after_tax0Mercedes-Benz A-Classsedan201939000noSunMikeStanley555342396M44070.01Audi A6sedan202167800yesMonSamBrittany887766234F76614.02Nissan Altimasedan201517500noSunMikeTodd998573477M19775.03Chevrolet EquinoxSUV20139600noWedTurnerJasime342234563F10848.04Hyundai Accenthatchback201723000yesThurMaddySam570566354M25990.05Porsche Cayennecoupe202182000yesFriMikeMorgan968258639F92660.06Volkswagen Jettasedan20003500noTueTurnerAaron557275923M3955.07Audi A6sedan202078444noSatBrittanyShelby223955366F88642.08Jeep WranglerSUV201733553yesFriMikeSam877425852M37915.09Volkswagen Jettasedan20129855noTueSamJessie885354544F11136.010Hyundai Accenthatchback201417434noMonMaddyTaylor870566354F19700.011Hyundai Accenthatchback20117434noWedMaddyMonte870066354M8400.012Mercedes-Benz A-Classhatchback201525453yesTueMikeAlyssa579521683F28762.013Nissan Altimasedan201010983noMonTurnerFelix994853335M12411.014Chevrolet EquinoxSUV201623998yesFriMikeKyle947577792M27118.015BMW M8coupe2021158000yesWedMaddyNicole338559922F178540.016Toyota 4RunnerSUV202254000noThurMikeJan462375343F61020.017Audi A6sedan201558444yesSatBrittanyQatava223855366M66042.018Jaguar XFsedan201957744yesSunTurnerTaylor884352886F65251.019Volkswagen Jettasedan20042235noTueTurnerGit995358322M2526.020Honda Civicsedan201822333noFriMikeJon334642443M25236.021BMW M8coupe2020140553noWedMaddySal326234886M158825.022Ford Maverickpickup201827433noMonSamMurry588845355M30999.023Jeep WranglerSUV202143553yesFriMikeDon277425852M49215.024Audi A6sedan202178444noThurBrittanyQatava223855366M88642.025Genesis GV80SUV202180444yesMonMikeSelena994447745F90902.026Porsche Cayennecoupe201552000noThurTurnerEmily958258639F58760.027Volkswagen Jettasedan201425356noWedSamPam995538822F28652.028Maserati LevanteSUV2020104325yesMonMikeCam452685274M117887.029Hyundai Accenthatchback201717434noThursMaddyBob70066354M19700.030Honda Civicsedan20002333noSatBrittanyAllen134642443M2636.031Chevrolet Camarocoupe201876550yesWedTurnerSarah552422222F86501.032Maserati LevanteSUV2020134325yesSunMikeTodd952685274M151787.033Mercedes-Benz A-Classsedan202144032yesMonTurnerJon996435345M49756.034Ford Maverickpickup201336033yesSunTurnerBailey508845355F40717.035Jeep WranglerSUV202143553yesFriMikeDon277425852M49215.036Porsche 911coupe2021185543yesMonSamCam452685274M209664.037Hyundai Accenthatchback201513434yesThursBrittanyDon277425852M15180.038Hyundai Accenthatchback201513434yesThursBrittanyDon277425852M15180.039Cadillac Escaladesedan201785474noTueMikeHarris885437455M96586.040Genesis GV80SUV202078422yesMonSamRachel995943645F88617.041Jeep WranglerSUV20023553noSunBrittanyPorsche277425858F4015.042Genesis GV80SUV202077842yesSatMikeEdward885352535M87961.043Cadillac Escaladesedan202048422yesMonSamRachel995943645F54717.044Bentley BentaygaSUV2020232000noWedMikeGabrielle885353455F262160.0
In: def proft_margin(price, finance):
            if finance == “N”:
                   if price < 10000
                         return “LOW” 
                   elif price >= 10000 and price < 25000:
                         return “MED” 
                   else:
                          return “HIGH” 
            else: 
                    if price < 7500
                         return “LOW” 
                   elif price >= 7500 and price < 20000:
                         return “MED” 
                   else:
                          return “HIGH” 
In: df[“profit_margin”] = np.vectorize(profit_margin) (df[“price”], df[“finance”])
In: df
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysexprice_after_taxprofit_margin0Mercedes-Benz A-Classsedan201939000noSunMikeStanley555342396M44070.0HIGH1Audi A6sedan202167800yesMonSamBrittany887766234F76614.0HIGH2Nissan Altimasedan201517500noSunMikeTodd998573477M19775.0MED3Chevrolet EquinoxSUV20139600noWedTurnerJasime342234563F10848.0LOW4Hyundai Accenthatchback201723000yesThurMaddySam570566354M25990.0HIGH5Porsche Cayennecoupe202182000yesFriMikeMorgan968258639F92660.0HIGH6Volkswagen Jettasedan20003500noTueTurnerAaron557275923M3955.0LOW7Audi A6sedan202078444noSatBrittanyShelby223955366F88642.0HIGH8Jeep WranglerSUV201733553yesFriMikeSam877425852M37915.0HIGH9Volkswagen Jettasedan20129855noTueSamJessie885354544F11136.0LOW10Hyundai Accenthatchback201417434noMonMaddyTaylor870566354F19700.0MED11Hyundai Accenthatchback20117434noWedMaddyMonte870066354M8400.0LOW12Mercedes-Benz A-Classhatchback201525453yesTueMikeAlyssa579521683F28762.0HIGH13Nissan Altimasedan201010983noMonTurnerFelix994853335M12411.0MED14Chevrolet EquinoxSUV201623998yesFriMikeKyle947577792M27118.0HIGH15BMW M8coupe2021158000yesWedMaddyNicole338559922F178540.0HIGH16Toyota 4RunnerSUV202254000noThurMikeJan462375343F61020.0HIGH17Audi A6sedan201558444yesSatBrittanyQatava223855366M66042.0HIGH18Jaguar XFsedan201957744yesSunTurnerTaylor884352886F65251.0HIGH19Volkswagen Jettasedan20042235noTueTurnerGit995358322M2526.0LOW20Honda Civicsedan201822333noFriMikeJon334642443M25236.0MED21BMW M8coupe2020140553noWedMaddySal326234886M158825.0HIGH22Ford Maverickpickup201827433noMonSamMurry588845355M30999.0HIGH23Jeep WranglerSUV202143553yesFriMikeDon277425852M49215.0HIGH24Audi A6sedan202178444noThurBrittanyQatava223855366M88642.0HIGH25Genesis GV80SUV202180444yesMonMikeSelena994447745F90902.0HIGH26Porsche Cayennecoupe201552000noThurTurnerEmily958258639F58760.0HIGH27Volkswagen Jettasedan201425356noWedSamPam995538822F28652.0HIGH28Maserati LevanteSUV2020104325yesMonMikeCam452685274M117887.0HIGH29Hyundai Accenthatchback201717434noThursMaddyBob70066354M19700.0MED30Honda Civicsedan20002333noSatBrittanyAllen134642443M2636.0LOW31Chevrolet Camarocoupe201876550yesWedTurnerSarah552422222F86501.0HIGH32Maserati LevanteSUV2020134325yesSunMikeTodd952685274M151787.0HIGH33Mercedes-Benz A-Classsedan202144032yesMonTurnerJon996435345M49756.0HIGH34Ford Maverickpickup201336033yesSunTurnerBailey508845355F40717.0HIGH35Jeep WranglerSUV202143553yesFriMikeDon277425852M49215.0HIGH36Porsche 911coupe2021185543yesMonSamCam452685274M209664.0HIGH37Hyundai Accenthatchback201513434yesThursBrittanyDon277425852M15180.0MED38Hyundai Accenthatchback201513434yesThursBrittanyDon277425852M15180.0MED39Cadillac Escaladesedan201785474noTueMikeHarris885437455M96586.0HIGH40Genesis GV80SUV202078422yesMonSamRachel995943645F88617.0HIGH41Jeep WranglerSUV20023553noSunBrittanyPorsche277425858F4015.0LOW42Genesis GV80SUV202077842yesSatMikeEdward885352535M87961.0HIGH43Cadillac Escaladesedan202048422yesMonSamRachel995943645F54717.0HIGH44Bentley BentaygaSUV2020232000noWedMikeGabrielle885353455F262160.0HIGH
In: df.describe()
Out: 
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
yearpricesocial_securityprice_after_taxcount45.00000045.0000004.500000e+0145.000000mean2016.22222254373.3777786.358065e+0861441.888889std5.60393150910.9154413.096242e+0857529.393065min2000.0000002235.0000007.006635e+072526.00000025%2015.00000017434.0000003.346424e+0819700.00000050%2018.00000043553.0000005.795217e+0849215.00000075%2020.00000078422.0000009.475778e+0888617.000000max2022.000000232000.0000009.985735e+08262160.000000
In: df.describe().transpose()
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
countmeanstdmin25%50%75%maxyear45.02.016222e+035.603931e+002000.02015.02018.02020.02022.0price45.05.437338e+045.091092e+042235.017434.043553.078422.0232000.0social_security45.06.358065e+083.096242e+0870066354.0334642443.0579521683.0947577792.0998573477.0price_after_tax45.06.144189e+045.752939e+042526.019700.049215.088617.0262160.0
In:df.sort_values(“price”)
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
cartypeyearpricefinancedaydealercustomersocial_securitysexprice_after_taxprofit_margin19Volkswagen Jettasedan20042235noTueTurnerGit995358322M2526.0LOW30Honda Civicsedan20002333noSatBrittanyAllen134642443M2636.0LOW6Volkswagen Jettasedan20003500noTueTurnerAaron557275923M3955.0LOW41Jeep WranglerSUV20023553noSunBrittanyPorsche277425858F4015.0LOW11Hyundai Accenthatchback20117434noWedMaddyMonte870066354M8400.0LOW3Chevrolet EquinoxSUV20139600noWedTurnerJasime342234563F10848.0LOW9Volkswagen Jettasedan20129855noTueSamJessie885354544F11136.0LOW13Nissan Altimasedan201010983noMonTurnerFelix994853335M12411.0MED38Hyundai Accenthatchback201513434yesThursBrittanyDon277425852M15180.0MED37Hyundai Accenthatchback201513434yesThursBrittanyDon277425852M15180.0MED10Hyundai Accenthatchback201417434noMonMaddyTaylor870566354F19700.0MED29Hyundai Accenthatchback201717434noThursMaddyBob70066354M19700.0MED2Nissan Altimasedan201517500noSunMikeTodd998573477M19775.0MED20Honda Civicsedan201822333noFriMikeJon334642443M25236.0MED4Hyundai Accenthatchback201723000yesThurMaddySam570566354M25990.0HIGH14Chevrolet EquinoxSUV201623998yesFriMikeKyle947577792M27118.0HIGH27Volkswagen Jettasedan201425356noWedSamPam995538822F28652.0HIGH12Mercedes-Benz A-Classhatchback201525453yesTueMikeAlyssa579521683F28762.0HIGH22Ford Maverickpickup201827433noMonSamMurry588845355M30999.0HIGH8Jeep WranglerSUV201733553yesFriMikeSam877425852M37915.0HIGH34Ford Maverickpickup201336033yesSunTurnerBailey508845355F40717.0HIGH0Mercedes-Benz A-Classsedan201939000noSunMikeStanley555342396M44070.0HIGH23Jeep WranglerSUV202143553yesFriMikeDon277425852M49215.0HIGH35Jeep WranglerSUV202143553yesFriMikeDon277425852M49215.0HIGH33Mercedes-Benz A-Classsedan202144032yesMonTurnerJon996435345M49756.0HIGH43Cadillac Escaladesedan202048422yesMonSamRachel995943645F54717.0HIGH26Porsche Cayennecoupe201552000noThurTurnerEmily958258639F58760.0HIGH16Toyota 4RunnerSUV202254000noThurMikeJan462375343F61020.0HIGH18Jaguar XFsedan201957744yesSunTurnerTaylor884352886F65251.0HIGH17Audi A6sedan201558444yesSatBrittanyQatava223855366M66042.0HIGH1Audi A6sedan202167800yesMonSamBrittany887766234F76614.0HIGH31Chevrolet Camarocoupe201876550yesWedTurnerSarah552422222F86501.0HIGH42Genesis GV80SUV202077842yesSatMikeEdward885352535M87961.0HIGH40Genesis GV80SUV202078422yesMonSamRachel995943645F88617.0HIGH7Audi A6sedan202078444noSatBrittanyShelby223955366F88642.0HIGH24Audi A6sedan202178444noThurBrittanyQatava223855366M88642.0HIGH25Genesis GV80SUV202180444yesMonMikeSelena994447745F90902.0HIGH5Porsche Cayennecoupe202182000yesFriMikeMorgan968258639F92660.0HIGH39Cadillac Escaladesedan201785474noTueMikeHarris885437455M96586.0HIGH28Maserati LevanteSUV2020104325yesMonMikeCam452685274M117887.0HIGH32Maserati LevanteSUV2020134325yesSunMikeTodd952685274M151787.0HIGH21BMW M8coupe2020140553noWedMaddySal326234886M158825.0HIGH15BMW M8coupe2021158000yesWedMaddyNicole338559922F178540.0HIGH36Porsche 911coupe2021185543yesMonSamCam452685274M209664.0HIGH44Bentley BentaygaSUV2020232000noWedMikeGabrielle885353455F262160.0HIGH
In: df.sort_values([“price”, “sexr”])
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb



























car
type
year
price
finance
day
dealer
customer
social_security
sex
price_after_tax
profit_margin


19
Volkswagen Jetta
sedan
2004
2235
no
Tue
Turner
Git
995358322
M
2526.0
LOW
30
Honda Civic
sedan
2000
2333
no
Sat
Brittany
Allen
134642443
M
2636.0
LOW
6
Volkswagen Jetta
sedan
2000
3500
no
Tue
Turner
Aaron
557275923
M
3955.0
LOW
41
Jeep Wrangler
SUV
2002
3553
no
Sun
Brittany
Porsche
277425858
F
4015.0
LOW
11
Hyundai Accent
hatchback
2011
7434
no
Wed
Maddy
Monte
870066354
M
8400.0
LOW
3
Chevrolet Equinox
SUV
2013
9600
no
Wed
Turner
Jasime
342234563
F
10848.0
LOW
9
Volkswagen Jetta
sedan
2012
9855
no
Tue
Sam
Jessie
885354544
F
11136.0
LOW
13
Nissan Altima
sedan
2010
10983
no
Mon
Turner
Felix
994853335
M
12411.0
MED
37
Hyundai Accent
hatchback
2015
13434
yes
Thurs
Brittany
Don
277425852
M
15180.0
MED
38
Hyundai Accent
hatchback
2015
13434
yes
Thurs
Brittany
Don
277425852
M
15180.0
MED
10
Hyundai Accent
hatchback
2014
17434
no
Mon
Maddy
Taylor
870566354
F
19700.0
MED
29
Hyundai Accent
hatchback
2017
17434
no
Thurs
Maddy
Bob
70066354
M
19700.0
MED
2
Nissan Altima
sedan
2015
17500
no
Sun
Mike
Todd
998573477
M
19775.0
MED
20
Honda Civic
sedan
2018
22333
no
Fri
Mike
Jon
334642443
M
25236.0
MED
4
Hyundai Accent
hatchback
2017
23000
yes
Thur
Maddy
Sam
570566354
M
25990.0
HIGH
14
Chevrolet Equinox
SUV
2016
23998
yes
Fri
Mike
Kyle
947577792
M
27118.0
HIGH
27
Volkswagen Jetta
sedan
2014
25356
no
Wed
Sam
Pam
995538822
F
28652.0
HIGH
12
Mercedes-Benz A-Class
hatchback
2015
25453
yes
Tue
Mike
Alyssa
579521683
F
28762.0
HIGH
22
Ford Maverick
pickup
2018
27433
no
Mon
Sam
Murry
588845355
M
30999.0
HIGH
8
Jeep Wrangler
SUV
2017
33553
yes
Fri
Mike
Sam
877425852
M
37915.0
HIGH
34
Ford Maverick
pickup
2013
36033
yes
Sun
Turner
Bailey
508845355
F
40717.0
HIGH
0
Mercedes-Benz A-Class
sedan
2019
39000
no
Sun
Mike
Stanley
555342396
M
44070.0
HIGH
23
Jeep Wrangler
SUV
2021
43553
yes
Fri
Mike
Don
277425852
M
49215.0
HIGH
35
Jeep Wrangler
SUV
2021
43553
yes
Fri
Mike
Don
277425852
M
49215.0
HIGH
33
Mercedes-Benz A-Class
sedan
2021
44032
yes
Mon
Turner
Jon
996435345
M
49756.0
HIGH
43
Cadillac Escalade
sedan
2020
48422
yes
Mon
Sam
Rachel
995943645
F
54717.0
HIGH
26
Porsche Cayenne
coupe
2015
52000
no
Thur
Turner
Emily
958258639
F
58760.0
HIGH
16
Toyota 4Runner
SUV
2022
54000
no
Thur
Mike
Jan
462375343
F
61020.0
HIGH
18
Jaguar XF
sedan
2019
57744
yes
Sun
Turner
Taylor
884352886
F
65251.0
HIGH
17
Audi A6
sedan
2015
58444
yes
Sat
Brittany
Qatava
223855366
M
66042.0
HIGH
1
Audi A6
sedan
2021
67800
yes
Mon
Sam
Brittany
887766234
F
76614.0
HIGH
31
Chevrolet Camaro
coupe
2018
76550
yes
Wed
Turner
Sarah
552422222
F
86501.0
HIGH
42
Genesis GV80
SUV
2020
77842
yes
Sat
Mike
Edward
885352535
M
87961.0
HIGH
40
Genesis GV80
SUV
2020
78422
yes
Mon
Sam
Rachel
995943645
F
88617.0
HIGH
7
Audi A6
sedan
2020
78444
no
Sat
Brittany
Shelby
223955366
F
88642.0
HIGH
24
Audi A6
sedan
2021
78444
no
Thur
Brittany
Qatava
223855366
M
88642.0
HIGH
25
Genesis GV80
SUV
2021
80444
yes
Mon
Mike
Selena
994447745
F
90902.0
HIGH
5
Porsche Cayenne
coupe
2021
82000
yes
Fri
Mike
Morgan
968258639
F
92660.0
HIGH
39
Cadillac Escalade
sedan
2017
85474
no
Tue
Mike
Harris
885437455
M
96586.0
HIGH
28
Maserati Levante
SUV
2020
104325
yes
Mon
Mike
Cam
452685274
M
117887.0
HIGH
32
Maserati Levante
SUV
2020
134325
yes
Sun
Mike
Todd
952685274
M
151787.0
HIGH
21
BMW M8
coupe
2020
140553
no
Wed
Maddy
Sal
326234886
M
158825.0
HIGH
15
BMW M8
coupe
2021
158000
yes
Wed
Maddy
Nicole
338559922
F
178540.0
HIGH
36
Porsche 911
coupe
2021
185543
yes
Mon
Sam
Cam
452685274
M
209664.0
HIGH
44
Bentley Bentayga
SUV
2020
232000
no
Wed
Mike
Gabrielle
885353455
F
262160.0






In: df[“price”].max()
Out: 232000
In: df[“price”].min()
Out: 2235
In: df[“price”].idxmax()
Out: 44
In: df.iloc(44)
Out: 
car                Bentley Bentayga
type                            SUV
year                           2020
price                        232000
finance                          no
day                             Wed
dealer                         Mike
customer                  Gabrielle
social_security           885353455
sex                               F
price_after_tax            262160.0
profit_margin                  HIGH
Name: 44, dtype: object
In: df.iloc[df[“price”].idxmax()]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In: df[“sex”].value_counts()
Out: 
M    26
F    19
Name: sex, dtype: int64
In: df[“car”].value_counts()
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In: df[“sex”] = df[“sex”].replace(to_replace=”M”, value=“male”)
In: df
Out: 
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In: df[“sex”] = df[“sex”].replace(to_replace=”F”, value=“female”)
In:df
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In: df.duplicate()
Out:
0     False
1     False
2     False
3     False
4     False
5     False
6     False
7     False
8     False
9     False
10    False
11    False
12    False
13    False
14    False
15    False
16    False
17    False
18    False
19    False
20    False
21    False
22    False
23    False
24    False
25    False
26    False
27    False
28    False
29    False
30    False
31    False
32    False
33    False
34    False
35     True
36    False
37    False
38     True
39    False
40    False
41    False
42    False
43    False
44    False
dtype: bool
in: df[df.duplicated()]
Out:



car
type
year
price
finance
day
dealer
customer
social_security
sex
price_after_tax
profit_margin
35
Jeep Wrangler
SUV
2021
43553
Y
Fri
Mike
Don
277425852
M
49215.0
HIGH
38
Hyundai Accent
hatchback
2015
13434
Y
Thurs
Brittany
Don
277425852
M
15180.0
MED

In: df[df[“car”] == “Jeep Wrangler”] 
Out: 
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb
…
In: df[“car”].unique()
Out: 
array(['Stanley', 'Brittany', 'Todd', 'Jasime', 'Sam', 'Morgan', 'Aaron',
       'Shelby', 'Jessie', 'Taylor', 'Monte', 'Alyssa', 'Felix', 'Kyle',
       'Nicole', 'Jan', 'Qatava', 'Git', 'Jon', 'Sal', 'Murry', 'Don',
       'Selena', 'Emily', 'Pam', 'Cam', 'Bob', 'Allen', 'Sarah', 'Bailey',
       'Harris', 'Rachel', 'Porsche', 'Edward', 'Gabrielle'], dtype=object)
In: df[“car”].nunique()
Out: 19
In: df[“price”].between(10000,20000)
Out:
0     False
1     False
2      True
3     False
4     False
5     False
6     False
7     False
8     False
9     False
10     True
11    False
12    False
13     True
14    False
15    False
16    False
17    False
18    False
19    False
20    False
21    False
22    False
23    False
24    False
25    False
26    False
27    False
28    False
29     True
30    False
31    False
32    False
33    False
34    False
35    False
36    False
37     True
38     True
39    False
40    False
41    False
42    False
43    False
44    False
Name: price, dtype: bool
In: df[df[“price”].between(10000,20000)]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
cartypeyearpricefinancedaydealercustomersocial_securitysexprice_after_taxprofit_margin2Nissan Altimasedan201517500NSunMikeTodd998573477M19775.0MED10Hyundai Accenthatchback201417434NMonMaddyTaylor870566354F19700.0MED13Nissan Altimasedan201010983NMonTurnerFelix994853335M12411.0MED29Hyundai Accenthatchback201717434NThursMaddyBob70066354M19700.0MED37Hyundai Accenthatchback201513434YThursBrittanyDon277425852M15180.0MED38Hyundai Accenthatchback201513434YThursBrittanyDon277425852M15180.0MED

Group By

In: df.groupby(“dealer”).sum()
Out: 
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
yearpricesocial_securityprice_after_taxdealerBrittany140882480861638586103280337.0Maddy121003638553046060224411155.0Mike323031099353113345310671242269.0Sam141264428315802077519500399.0Turner181132926776790036590330725.0
In: df.groupby(“dealer”).sum().[“price”]
Out:
dealer
Brittany     248086
Maddy        363855
Mike        1099353
Sam          442831
Turner       292677
Name: price, dtype: int64
In: df.groupby(“dealer”).sum().index
Out:Index(['Brittany', 'Maddy', 'Mike', 'Sam', 'Turner'], dtype='object', name='dealer')
In: df.groupby(“dealer”).sum().columns
Out: 
Index(['year', 'price', 'social_security', 'price_after_tax'], dtype='object')
In: df.groupby(“dealer”).mean()
Out:

year
price
social_security
price_after_tax


dealer








Brittany
2012.571429
35440.857143
2.340837e+08
40048.142857
Maddy
2016.666667
60642.500000
5.076767e+08
68525.833333
Mike
2018.937500
68709.562500
7.084082e+08
77641.812500
Sam
2018.000000
63261.571429
8.288682e+08
71485.571429
Turner
2012.555556
32519.666667
7.544485e+08
36747.222222

In: df.groupby([“dealer”, “year”]).sum()
Out: 





price
social_security
price_after_tax
dealer
year






Brittany
2000
2333
134642443
2636.0
2002
3553
277425858
4015.0
2015
85312
778707070
96402.0
2020
78444
223955366
88642.0
2021
78444
223855366
88642.0
Maddy
2011
7434
870066354
8400.0
2014
17434
870566354
19700.0
2017
40434
640632708
45690.0
2020
140553
326234886
158825.0
2021
158000
338559922
178540.0
Mike
2015
42953
1578095160
48537.0
2016
23998
947577792
27118.0
2017
119027
1762863307
134501.0
2018
22333
334642443
25236.0
2019
39000
555342396
44070.0
2020
548492
3176076538
619795.0
2021
249550
2517558088
281992.0
2022
54000
462375343
61020.0
Sam
2012
9855
885354544
11136.0
2014
25356
995538822
28652.0
2018
27433
588845355
30999.0
2020
126844
1991887290
143334.0
2021
253343
1340451508
286278.0
Turner
2000
3500
557275923
3955.0
2004
2235
995358322
2526.0
2010
10983
994853335
12411.0
2013
45633
851079918
51565.0
2015
52000
958258639
58760.0
2018
76550
552422222
86501.0
2019
57744
884352886
65251.0
2021
44032
996435345
49756.0

In: df.groupby([“dealer”, “year”]).sum().index
Out: 
MultiIndex([('Brittany', 2000),
            ('Brittany', 2002),
            ('Brittany', 2015),
            ('Brittany', 2020),
            ('Brittany', 2021),
            (   'Maddy', 2011),
            (   'Maddy', 2014),
            (   'Maddy', 2017),
            (   'Maddy', 2020),
            (   'Maddy', 2021),
            (    'Mike', 2015),
            (    'Mike', 2016),
            (    'Mike', 2017),
            (    'Mike', 2018),
            (    'Mike', 2019),
            (    'Mike', 2020),
            (    'Mike', 2021),
            (    'Mike', 2022),
            (     'Sam', 2012),
            (     'Sam', 2014),
            (     'Sam', 2018),
            (     'Sam', 2020),
            (     'Sam', 2021),
            (  'Turner', 2000),
            (  'Turner', 2004),
            (  'Turner', 2010),
            (  'Turner', 2013),
            (  'Turner', 2015),
            (  'Turner', 2018),
            (  'Turner', 2019),
            (  'Turner', 2021)],
           names=['dealer', 'year'])
In: df.groupby([“dealer”, “year”]).sum().columns
Out: Index(['price', 'social_security', 'price_after_tax'], dtype='object')
In: dealer_year = df.groupby([“dealer”, “year”]).sum()
Out:

price
social_security
price_after_tax




dealer
year






Brittany
2000
2333
134642443
2636.0
2002
3553
277425858
4015.0
2015
85312
778707070
96402.0
2020
78444
223955366
88642.0
2021
78444
223855366
88642.0
Maddy
2011
7434
870066354
8400.0
2014
17434
870566354
19700.0
2017
40434
640632708
45690.0
2020
140553
326234886
158825.0
2021
158000
338559922
178540.0
Mike
2015
42953
1578095160
48537.0
2016
23998
947577792
27118.0
2017
119027
1762863307
134501.0
2018
22333
334642443
25236.0
2019
39000
555342396
44070.0
2020
548492
3176076538
619795.0
2021
249550
2517558088
281992.0
2022
54000
462375343
61020.0
Sam
2012
9855
885354544
11136.0
2014
25356
995538822
28652.0
2018
27433
588845355
30999.0
2020
126844
1991887290
143334.0
2021
253343
1340451508
286278.0
Turner
2000
3500
557275923
3955.0
2004
2235
995358322
2526.0
2010
10983
994853335
12411.0
2013
45633
851079918
51565.0
2015
52000
958258639
58760.0
2018
76550
552422222
86501.0
2019
57744
884352886
65251.0
2021
44032
996435345
49756.0

In: dealer_year.loc(“Mike”)
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
pricesocial_securityprice_after_taxyear201542953157809516048537.020162399894757779227118.020171190271762863307134501.020182233333464244325236.020193900055534239644070.020205484923176076538619795.020212495502517558088281992.020225400046237534361020.0
In: dealer_year.loc[[“Mike”, “Brittany”]]
Out:
https://github.com/harblaith7/Pandas/blob/main/Pandas.ipynb 
pricesocial_securityprice_after_taxdealeryearMike201542953157809516048537.020162399894757779227118.020171190271762863307134501.020182233333464244325236.020193900055534239644070.020205484923176076538619795.020212495502517558088281992.020225400046237534361020.0Brittany200023331346424432636.0200235532774258584015.020158531277870707096402.020207844422395536688642.020217844422385536688642.0
In: dealer_year.loc[(“Mike”, 2019)]
Out: 
price                  39000.0
social_security    555342396.0
price_after_tax        44070.0
Name: (Mike, 2019), dtype: float64


