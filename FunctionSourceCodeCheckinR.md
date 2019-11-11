#Check the source code in R

In daily life when we use the functions from a package. Some times we may confront with many unexpected bugs or need to trim this function for applying to out own problem. In either circumstance, we need to check the source code of r function.

**There are 2 methods that we can access the source code:**

## Download directly from CRAN
Take the example of pwrAB package, you can find it from CRAN index,see [here](https://cran.r-project.org/web/packages/pwrAB/index.html). Download the **.tar.gz**, it will include all the function embeded in the package. ![Alt Image Text](https://raw.githubusercontent.com/diana12333/RNotebook/master/pics/Screen%20Shot%202019-11-11%20at%2010.52.03%20AM.png "Optional Title")
Some package might provide their github reposite, you can also pull code from their github webpacge.

Don't forget to give a star for their contribution!
## Check source code from R console
There is a r function that can be use to see the function source code.
take function sample as example:

```
getAnywhere('sample')
```
it will return:
![](https://raw.githubusercontent.com/diana12333/RNotebook/master/pics/Screen%20Shot%202019-11-11%20at%2011.03.20%20AM.png)

if more than one objects found see
```
getAnywhere(summarise())
```
it will return,
![](https://raw.githubusercontent.com/diana12333/RNotebook/master/pics/Screen%20Shot%202019-11-11%20at%2011.08.47%20AM.png)
 your can select summarise within **plyr** by 
 
```R
getAnywhere(summarise())[1]
```
## Further check C/c++ source code
sometimes the code shows in the below will shows
>.Internal(max.col(as.matrix(m), tieM))


this means the source code was written by Infrastructure development language like C/C++.
we can reach this by using *show_c_source* in **pryr** package. It will redirect to the github package for the low-layer source code.
>show\_c\_source(.Internal(max.col(as.matrix(m), tieM))
