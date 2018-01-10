# portfolio_optimization
This is the final project of STAT 222 (Statistics master program capstone project) Spring 2017 at UC Berkeley. For more details, please check out the final report (by each individual student) and the final presentation (by a group of 3) in this repository.

# Introduction
In the current project, we tried to build an ”optimal” portfolio. What for a portfolio can be called ”optimal”? One with low out-of-sample variance, and high return.
To build ”optimal” portfolios, we used the adjusted monthly return of various equities as well as multiple ”risk-free” government bonds, and the cross-sectional characteristics/factors such as market equity, book-to-market ratio etc. In our project, we first explored several portfolio optimization methods that only use historic monthly return data in solving some forms of optimization problems. We also explored two factor-based methods. These methods not only use historic monthly return data, but also historic cross-sectional characteristics/factors. One such method models the returns of equities directly, similar to the Fama- French three-factor model. The other models the portfolio weights directly by adjusting the weights of a value equally distributed portfolio using 3 cross-sectional characteristics: the market equity (me), the book-to-market ratio (btm), and the compounded historic return. These cross-sectional characteristics/factors are from the fundamentals data revealed by companies’ quarterly/annual earning reports.

# Data description
The historic monthly return data used for this project can be easily obtained by using R’s quantmod package. When provided with the equity symbol, start data, and end date, the quantmod package can retrieve the historic data of an equity from several sources and store it as a time series object in xts format. The raw data contains the daily open, close, high, low, adjusted prices, and volume. we used quantmod’s monthlyReturn function to pre-process the data and extracted the adjusted monthly return for equities.
The historic cross-sectional characteristics/factors data of companies can be obtained using the Wharton Research Data Services (WRDS). Hundreds of factors of companies are available from WRDS, among which we only used the equity price, the shares outstanding, and the book value per share. Together with the monthly return data, we were able to calculate the 3 cross-sectional characteristics: the market equity, the book-to-value ratio, and the compounded monthly return.
We selected 556 equities with full records (monthly return, equity price, shares outstanding, and book value per share) from 1986 to 2015 from thousands of equities from NYSE and NASDAQ . 

# Optimization methods
In this project, we solved different convex optimization problems using CVXPY

