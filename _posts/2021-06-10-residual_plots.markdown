---
layout: post
title:      "Residual Plots"
date:       2021-06-11 01:24:41 +0000
permalink:  residual_plots
---

As I've developed through the Flatiron lessons and project's thus far( 2nd project), I had to learn how to use residual plots in regression pretty well. Residual analysis are used to verify that model is linear and that you can therefor go ahead and make conclusions about your model.  For the a linear model to make sense, the residuals must: 
1.	Vary constantly 
2.	Be normally distributed 
3.	And be independent of each other
For number one, residuals must vary constantly, around zero.  In my second module project for example, the residuals varied consistently through most of the data. However, as my predictor increase to the extremes, the residuals (errors) became also varied increasingly positive.  That indicated to me that my data was not linear towards the higher end.  If you were to plot it on a Q-Q plot, the residuals would tail highly positive in the top right corner.  

One limitations of these residual plots is that the residuals is that they depend on the scale (in my project mentioned above, I scaled all the data appropriately before modeling so my residual plot did not depend much on scale). The standard deviation of the residuals at different values of the predictors can vary, even if the variances are constant. So, it’s difficult to use residuals to determine whether an observation is an outlier, or to assess whether the variance is constant.

An alternative is to use studentized residuals. A studentized residual is calculated by dividing the residual by an estimate of its standard deviation. The standard deviation for each residual is computed with the observation excluded. For this reason, studentized residuals are sometimes referred to as externally studentized residuals. Studentized residuals are more effective in detecting outliers and in assessing the equal variance assumption. The Studentized Residual by Row Number plot essentially conducts a t test for each residual. Studentized residuals falling outside the red limits are potential outliers.

Now to look at outliers. An observation is considered an outlier if it is extreme, relative to other response values. In contrast, some observations have extremely high or low values for the predictor variable, relative to the other values. These are referred to as high leverage observations. The fact that an observation is an outlier or has high leverage is not necessarily a problem in regression.

But some of these extreme outliers (high leverage) can actually move the regression line and you would see it clearly on a residual plot.  The outlier residual would actually move the entire centerline of the residual plot toward that one point. So how would you figure out which outliers are going to be a problem for regression?

Use Cook's D.  It measures how much the model coefficient estimates would change if an observation were to be removed from the data.  There is one for each data point,  and the higher the Cook's D, the greater the influence. Generally, Cook's D above 1.0 would indicate influential and below not-influential.

So if you have influential points, don't immediately get rid of them.  They might be important.  You might need more data, or you need to evaluate a further.

