---
title: "Corona Virus Report"
author:
- familyname: XXXX
  othernames: XXX
  address: Monash Universtidy
  email: XXX
  correspondingauthor: true
  qualifications:  XXX
- familyname: Al-Hindi
  othernames: Ibrahim
  address: Monash University
  qualifications: Student
- familyname: XXX
  othernames: XXX
  address: XXX
  email: XXX
  correspondingauthor: true
  qualifications:  XXX
department: Our consultancy \newline add names &\newline add names
organization: Australian Government COVID19
bibliography: references.bib
biblio-style: authoryear-comp
linestretch: 1.5
output:
  bookdown::pdf_document2:
    template: monashreport2.tex
    fig_caption: yes
    fig_height: 5
    fig_width: 8
    includes:
      in_header: preamble.tex
    keep_tex: yes
    number_sections: yes
    citation_package: biblatex
    toc: false
---





\section*{Country XX1 and YY1"}


```r
corona <- read_csv('Data/worldwidecases.csv')
```

```
## 
## -- Column specification --------------------------------------------------------
## cols(
##   dateRep = col_character(),
##   day = col_double(),
##   month = col_double(),
##   year = col_double(),
##   cases = col_double(),
##   deaths = col_double(),
##   countriesAndTerritories = col_character(),
##   geoId = col_character(),
##   countryterritoryCode = col_character(),
##   popData2018 = col_double(),
##   continentExp = col_character()
## )
```


```r
corona %>% 
  filter(year == 2020,
         countriesAndTerritories %in% c('Jordan', 'Saudi_Arabia')) %>% 
  group_by(countriesAndTerritories, month) %>%
  summarise(cases = sum(cases)) %>% 
  kable(caption = 'Jordan and Saudi cases per month in 2020')
```

```
## `summarise()` has grouped output by 'countriesAndTerritories'. You can override using the `.groups` argument.
```

\begin{table}

\caption{(\#tab:covid-table)Jordan and Saudi cases per month in 2020}
\centering
\begin{tabular}[t]{l|r|r}
\hline
countriesAndTerritories & month & cases\\
\hline
Jordan & 3 & 268\\
\hline
Jordan & 4 & 183\\
\hline
Jordan & 5 & 71\\
\hline
Saudi\_Arabia & 3 & 1453\\
\hline
Saudi\_Arabia & 4 & 19949\\
\hline
Saudi\_Arabia & 5 & 15734\\
\hline
\end{tabular}
\end{table}

As per \@ref(tab:covid-table)), Saudi Arabia had more cases in each month.


\section*{Country XX2 and YY2}

\section*{Country XX3 and YY3}



