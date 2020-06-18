# README

>Name: **Yuxiang Yao**
>
>UCD No. **17205995**
>
>Applicable Corpus: **Both small and large corpus**

## 1. File Description & Guidance

### 1.1 Submission Content:

- **README.md**: descriptive document
- **largesearch.py**: which can be used in large corpus 
- **smallsearch.py**: which can be used in small corpus 

### 1. 2 Project Structure:

- <u>documents</u>: file set for documents which will be used in searching 
- files:
  - <u>output.txt</u> **(generated)**:  files generated during the evaluation process which contains the result of the query
  - <u>porter.py:</u>  package which support stemming
  - <u>qrels.txt</u>: files that store the judgements
  - <u>queries.txt</u>: files that store the queries
  - <u>stopwords.txt</u>: file that store the stopwords
- <u>smallsearch.py</u> (or <u>largesearch.py</u>) python file which is used to execute the BM25 search and evaluation
- <u>record.json</u> **(generated)**: index file that store related information for searching 

### 1.3 smallsearch.py in small corpus

**Before you want to search keywords and evaluate the feedback, you should jump to the correct directory firstly. The following cmd command is one example:**

```
cd C:\Users\Public\small_corpus
```

#### 1.3.1 Part 1: BM25

In this part when you want to execute the search function by BM25, you can try following in the command:

```powershell
python smallsearch.py -m manual
```

After execution,  it will generate the index file if there doesn't exist the index file.  Here is content of the index file (name: 'record.json')

```
{
	"len_avg": 87,
    "doc_number": 1400,
    "len_doc1": 75,
    ......,
    "len_doc10": 28,
    "configur": {
        "appearance": 129,
        "occurrences": {
            "1": 1,
            "1000": 2,
            "1064": 3,
            "1066": 2,
            ......
            "971": 2
        }
    },
    ......
    "517": [
        "reaction-resist",
        "shock",
        .......
        "s",
        "ideal",
        "dissoci",
        "ga"
    ],
    
}
```

The 15 highest similarity score documents will be returned with their rank, document id and similarity score. Here is one demo:

```
Enter Query
investigate
1  243  2.47221504734603
2  463  2.4493770330518405
3  372  2.4437333071692326
4  126  2.3779826352274593
5  712  2.364727436591855
6  1162  2.3620941098250485
7  549  2.356845011803215
8  841  2.356845011803215
9  1305  2.356845011803215
10  1367  2.341236766691936
11  782  2.2881990405856456
12  713  2.2613651499177974
13  905  2.258956880322571
14  1163  2.256553734705206
15  780  2.2517627501304607
```

#### 1.3.2 Part 2:  Evaluation

In this part when you want to execute the evaluation function , you can try following in the command:

```powershell
python smallsearch.py -m evaluation
```

After execution, it will check whether there are one index file or one output file. If there isn't any index file, it will generate the  index file.it will calculate the result for queries and store the answer in output (the result is the set for the ***50 highest similarity score documents***). Here is one demo:

```
1 Q0 51 1 28.340832909768796 17205995
1 Q0 486 2 25.617045311568365 17205995
1 Q0 12 3 22.53952635402862 17205995
1 Q0 878 4 22.36043445848081 17205995
1 Q0 573 5 19.0012203530584 17205995
1 Q0 944 6 17.240971464118036 17205995
1 Q0 746 7 17.13675651436137 17205995
1 Q0 141 8 16.217160849823603 17205995
1 Q0 747 9 15.226926673147643 17205995
1 Q0 78 10 14.97534778459159 17205995
1 Q0 879 11 14.925846348053591 17205995
1 Q0 13 12 14.818227511882174 17205995
1 Q0 329 13 14.801570210468142 17205995
1 Q0 663 14 14.701826109180068 17205995
1 Q0 665 15 14.596924012569524 17205995
1 Q0 14 16 13.688199410318916 17205995
1 Q0 184 17 13.459884174044763 17205995
1 Q0 876 18 13.198028516647872 17205995
1 Q0 359 19 13.181501414920914 17205995
1 Q0 252 20 13.008831043878045 17205995
1 Q0 1144 21 12.858012064016744 17205995
1 Q0 332 22 12.523758325847753 17205995
1 Q0 202 23 12.482845551717189 17205995
1 Q0 792 24 12.448491907247742 17205995
1 Q0 685 25 12.448262942293576 17205995
1 Q0 875 26 12.43063022807486 17205995
1 Q0 56 27 12.372866153692321 17205995
1 Q0 729 28 11.914153165554982 17205995
1 Q0 1328 29 11.672054611261803 17205995
1 Q0 1186 30 11.5743199497424 17205995
1 Q0 435 31 11.34391210338687 17205995
1 Q0 526 32 11.04006355854848 17205995
1 Q0 29 33 11.028213842945215 17205995
1 Q0 629 34 10.984730579169605 17205995
1 Q0 414 35 10.836922754947253 17205995
1 Q0 305 36 10.738241020930479 17205995
1 Q0 1194 37 10.698731891649246 17205995
1 Q0 280 38 10.664274084915533 17205995
1 Q0 83 39 10.599462491664037 17205995
1 Q0 1034 40 10.511609572947151 17205995
1 Q0 781 41 10.301454294835374 17205995
1 Q0 1155 42 10.28108946811293 17205995
1 Q0 491 43 10.25058807376257 17205995
1 Q0 378 44 10.240735109127662 17205995
1 Q0 253 45 10.155048474101138 17205995
1 Q0 315 46 10.128208005519634 17205995
1 Q0 811 47 9.9882917605333 17205995
1 Q0 982 48 9.951234741151463 17205995
1 Q0 1003 49 9.917584854011057 17205995
1 Q0 1263 50 9.841220287321303 17205995
```

After that, it will use different evaluation methods to get the evaluation result；

```
Evaluation results:
precision: 0.09733333333333323
recall: 0.6500559634659205
P@10: 0.20648888888888964
R-precision: 0.37801397664277653
MAP: 0.3848369917488004
bpref: 0.35639515911383074
```

### 1.4 largesearch.py in large corpus

**Before you want to search keywords and evaluate the feedback, you should jump to the correct directory firstly. The following cmd command is one example:**

```
cd C:\Users\Public\large_corpus
```

#### 1.4.1 Part 1: BM25

In this part when you want to execute the search function by BM25, you can try following in the command:

```powershell
python largesearch.py -m manual
```

After execution,  it will generate the index file if there doesn't exist the index file.  Here is content of the index file (name: 'record.json')

```
{
	"len_avg": 3580,
    "doc_number": 6377,
    
    "len_docGX000-01-10544170": 454,
    "len_docGX000-09-2703409": 2815,
    ......,
    "len_docGX000-16-4063715": 6327,
    
    'word':{
    	"configur": {
    		"GX247-09-11628512": 1,
        	"GX247-12-2443694": 1,         
            ......
            "GX247-44-2509657": 1,
    	},
    	......
    }
   
   
   'passage':{
   		"GX048-30-16405504": {
			"open": 12,
			"skies": 1,
			......
            "state": 2,
            "kingdom": 2,
    	} 
   		.....
   }  
}
```

The 15 highest similarity score documents will be returned with their rank, document id and similarity score.  Here is one demo:

``` 
Enter Query
investigate
FIND INDEX FILE!
LOAD INDEX FILE......
QUERYING......
RANKING FEEDBACK......
Results for query [investigate]
1  GX236-59-10870854  1.5697205864936352
2  GX038-53-6323145  1.5617559395110443
3  GX007-22-11439805  1.5607341265633246
4  GX016-56-16261250  1.5607341265633246
5  GX004-02-9986199  1.5579310229290264
6  GX020-48-14364499  1.5556450527307175
7  GX042-71-5665734  1.5543779656438932
8  GX016-68-8167726  1.5531129409851843
9  GX005-25-4943422  1.552607507473989
10  GX024-47-13958310  1.5505890588428541
11  GX042-19-16587706  1.5503371217124096
12  GX054-25-11076408  1.5438153713352354
13  GX135-15-3862120  1.543066390776666
14  GX008-86-1780802  1.5418197035062982
15  GX147-22-10891733  1.5393323626208826
```

#### 1.4.2 Part 2:  Evaluation

In this part when you want to execute the evaluation function , you can try following in the command:

```powershell
python largesearch.py -m evaluation
```

After execution, it will check whether there are one index file or one output file. If there isn't any index file, it will generate the  index file and then it will calculate the result for queries and store the answer in output (the result is the set for the ***50 highest similarity score documents***). Here is one demo:

```
701 Q0 GX232-43-0102505 1 10.440180833846618 17205995
701 Q0 GX229-87-1373283 2 10.200449084235098 17205995
701 Q0 GX255-56-12408598 3 10.193727694707007 17205995
701 Q0 GX064-43-9736582 4 10.15107067620894 17205995
701 Q0 GX253-41-3663663 5 10.073485000373685 17205995
701 Q0 GX268-35-11839875 6 9.935560556692762 17205995
701 Q0 GX063-18-3591274 7 9.822182435690284 17205995
701 Q0 GX231-53-10990040 8 9.821533434642916 17205995
701 Q0 GX263-63-13628209 9 9.801939366674242 17205995
701 Q0 GX253-57-7230055 10 9.730696698953508 17205995
701 Q0 GX025-72-6112588 11 9.60204858483614 17205995
701 Q0 GX068-83-6288039 12 9.55149263810025 17205995
701 Q0 GX268-22-14058611 13 9.473350039760648 17205995
701 Q0 GX006-76-15945590 14 9.457910837269356 17205995
701 Q0 GX262-86-10646381 15 9.44495313946995 17205995
701 Q0 GX253-43-11798479 16 9.396350058557925 17205995
701 Q0 GX262-28-10252024 17 9.349279498181234 17205995
701 Q0 GX261-99-14766455 18 9.285708569021885 17205995
701 Q0 GX228-89-9137293 19 9.270093284406274 17205995
701 Q0 GX255-59-12399984 20 9.258233577655435 17205995
701 Q0 GX252-60-1822729 21 9.225924058451692 17205995
701 Q0 GX104-28-6788626 22 9.212656054260037 17205995
701 Q0 GX271-37-7577511 23 9.192741047941844 17205995
701 Q0 GX270-89-3515323 24 9.183052587150296 17205995
701 Q0 GX267-12-13936725 25 9.126167158227217 17205995
701 Q0 GX271-83-9629845 26 9.106465695933224 17205995
701 Q0 GX098-89-15335232 27 9.105121570077563 17205995
701 Q0 GX015-20-10573408 28 9.066378435283793 17205995
701 Q0 GX260-74-0957038 29 9.06571197118793 17205995
701 Q0 GX128-96-12152039 30 9.006049348255045 17205995
701 Q0 GX251-17-4053346 31 9.000232981203226 17205995
701 Q0 GX233-37-7282946 32 8.954592890364122 17205995
701 Q0 GX021-08-13644385 33 8.920986081197796 17205995
701 Q0 GX043-81-4336257 34 8.853726174781524 17205995
701 Q0 GX270-62-10329938 35 8.827011924675393 17205995
701 Q0 GX236-20-3341877 36 8.788630503713874 17205995
701 Q0 GX034-61-5088345 37 8.78721210621695 17205995
701 Q0 GX247-24-7579610 38 8.75310653301847 17205995
701 Q0 GX048-95-13732967 39 8.751828023209953 17205995
701 Q0 GX036-36-8703297 40 8.736370424078874 17205995
701 Q0 GX051-08-2365574 41 8.734565435402699 17205995
701 Q0 GX004-05-12123594 42 8.683351709353166 17205995
701 Q0 GX237-14-4316559 43 8.654170007950732 17205995
701 Q0 GX042-08-13377049 44 8.645731963293645 17205995
701 Q0 GX235-03-7888088 45 8.632439077699278 17205995
701 Q0 GX235-12-10767883 46 8.62380402959991 17205995
701 Q0 GX001-37-16595181 47 8.615468878554234 17205995
701 Q0 GX262-20-16148678 48 8.60599406592722 17205995
701 Q0 GX235-79-0358775 49 8.605583513240154 17205995
701 Q0 GX015-52-12130762 50 8.604312979941662 17205995
```

After that, it will use different evaluation methods to get the evaluation result；

```
Evaluation results:
precision: 0.3482926829268293
recall: 0.9107332122008522
P@10: 0.5743902439024389
R-precision: 0.5283152143968
MAP: 0.5587190708462201
bpref: 0.5581127427119493
```

## 2. Performance Statistics

>  All following statistics are based on my laptop performance. The configuration of my laptop(Thinkpad X1 Carbon) is shown as below:
>
> - RAM: 8GB
> - CPU: i7
> - Frequency: 2.70 GHz

### 2.1 Performance In Small Corpus

- Time for loading index file and searching *one word*: about **0.02** seconds 
- Time for generating index file: about **1** seconds
- Time for generating output file: about **40** seconds
- Time for finish the evaluation (without generating output file): about **0.02** seconds

### 2.2 Performance In Large Corpus

- Time for searching *one word* (without loading index file): about **0.02** seconds
- Time for loading index file: about **10** seconds
- Time for generating index file: about **70** seconds
- Time for generating output file: about **15** seconds
- Time for finish the evaluation (without generating output file):  about **0.03** seconds
