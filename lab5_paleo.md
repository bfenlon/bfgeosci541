#Lab Exercise Five
##Problem Set 1
1)
  > BivalvePresence <- BivalveAbundance
  
  > BivalvePresence[BivalvePresence>0] <- 1
  
  > sum(BivalvePresence["Miocene",])
  
  > [1] 634
  
2) 
  > max(BrachiopodAbundance["Pliocene",])/sum(BrachiopodAbundance["Pliocene",])
  
  > [1] 0.2222222
  
3)
  > gsOrdo <- function(x,interval) {

  > a <- sum(x[interval,])^2

  > b <- x[interval,]^2

  > c <- b/a

  > d <- 1-sum(c)

  > return(d)

  > }
  
  > gsOrdo(BrachiopodAbundance,"Late Ordovician")
  
  > [1] 0.9784588
  
4)
  > erebus <- function(x,interval) {
  
  > a <- x[interval,]

  > b <- a[a != 0]
  
  > c <- sum(b)

  > d <- b/c

  > e <- d*log(d)

  > f <- -sum(e)

  > return(f)

  > }
  
  > erebus(BivalveAbundance, "Late Cretaceous")
  
  > [1] 5.086654

5) 
  > erebus(BivalveAbundance, "Paleocene")
  
  > [1] 4.511875

6) The K-Pg extinction event resulted in a mass extinction of a large portion of the species on Earth some 66 million years ago. This number (0.8870025) does not seem to accurately represent how much biodiversity survived into the Paleocene.
  > erebus(BivalveAbundance, "Paleocene")/erebus(BivalveAbundance, "Late Cretaceous")
  
  > [1] 0.8870025

7) This number seems to be more appropriate for such a large mass extinction as the K-Pg.
  > exp(erebus(BivalveAbundance, "Paleocene"))/exp(erebus(BivalveAbundance, "Late Cretaceous"))

  > [1] 0.5628292
  
##Problem Set 2
1)
  > specnumber(BivalveAbundance["Miocene",])
  
  > [1] 634
  
2)
  > diversity(BrachiopodAbundance["Late Ordovician",], index="simpson")
  
  > [1] 0.9784588

3)
  > diversity(BivalveAbundance["Late Cretaceous",], index="shannon")
  
  > [1] 5.086654
  
4)
  > diversity(BivalveAbundance["Paleocene",], index="shannon")
  
  > [1] 4.511875
  
##Problem Set 3
1)
  > bivalveframe <- data.frame(bivalve_richness=apply(BivalveAbundance, 1, specnumber))

  > brachframe <- data.frame(brach_richness=apply(BrachiopodAbundance, 1, specnumber))
  
  > bivalveframe <- mutate(bivalveframe, names=dimnames(bivalveframe)[[1]])
  
  > brachframe <- mutate(brachframe, names=dimnames(bivalveframe)[[1]])
  
  > InOrder <- data.frame(names=c("Early Ordovician", "Middle Ordovician", "Late Ordovician", "Llandovery", "Wenlock", "Ludlow", "Pridoli", "Early Devonian", "Middle Devonian", "Late Devonian", "Mississippian", "Pennsylvanian" ,"Cisuralian", "Guadalupian", "Lopingian", "Early Triassic", "Middle Triassic", "Late Triassic", "Early Jurassic", "Middle Jurassic", "Late Jurassic", "Early Cretaceous", "Late Cretaceous", "Paleocene", "Eocene", "Oligocene", "Miocene", "Pliocene", "Pleistocene"))
  
  > bivalveframe <- bivalveframe[match(InOrder$names, bivalveframe$names),]
  
  > brachframe <- brachframe[match(InOrder$names, brachframe$names),]
  
  > corframe <- data.frame(brachframe, bivalveframe)

  > cor(corframe$brach_richness, corframe$bivalve_richness)
  
|                    |brach_richness |
|:------------------:|:-------------:|
|**bivalve_richness**|      -0.567194|

2)
> diversityframe <- data.frame(brach_diversity=apply(BrachiopodAbundance, 1, function (x, index="simpson", MARGIN=1, base=exp(1))

> {

>     x <- drop(as.matrix(x))

>     INDICES <- c("shannon", "simpson", "invsimpson")

>     index <- match.arg(index, INDICES)

>     if (length(dim(x)) > 1) {

>         total <- apply(x, MARGIN, sum)

>         x <- sweep(x, MARGIN, total, "/")

>     }

>     else {

>         x <- x/sum(x)

>     }

>     if (index == "shannon") 

>         x <- -x * log(x, base)

>     else x <- x * x

>     if (length(dim(x)) > 1) 

>         H <- apply(x, MARGIN, sum, na.rm = TRUE)

>     else H <- sum(x, na.rm = TRUE)

>     if (index == "simpson") 

>         H <- 1 - H

>     else if (index == "invsimpson") 

>         H <- 1/H

>     H

> }),

> bivalve_diversity=apply(BivalveAbundance, 1, function(x, index="simpson", MARGIN=1, base=exp(1))

> {

>     x <- drop(as.matrix(x))

>     INDICES <- c("shannon", "simpson", "invsimpson")

>     index <- match.arg(index, INDICES)

>     if (length(dim(x)) > 1) {

>         total <- apply(x, MARGIN, sum)

>         x <- sweep(x, MARGIN, total, "/")

>     }

>     else {

>         x <- x/sum(x)

>     }

>     if (index == "shannon") 

>         x <- -x * log(x, base)

>     else x <- x * x

>     if (length(dim(x)) > 1) 

>         H <- apply(x, MARGIN, sum, na.rm = TRUE)

>     else H <- sum(x, na.rm = TRUE)

>     if (index == "simpson") 

>         H <- 1 - H

>     else if (index == "invsimpson") 

>         H <- 1/H

>     H

> }))

> diversityframe <- mutate(diversityframe, names=dimnames(diversityframe)[[1]])

> diversityframe <- diversityframe[match(InOrder$names, diversityframe$names),]

> cor(diversityframe[,"brach_diversity"], diversityframe[,"bivalve_diversity"])

> [1] -0.2624135
