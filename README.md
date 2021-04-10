# AB-TESTING

Facebook has two different ways of bidding ads. These are called "maximum bidding" and "average bidding". The average bidding method of these two methods is the new one. We will find out whether the conversion rate of the new feature is higher than the old one by applying AB testing.

AB TEST also known as split testing is process of comparing two groups and measuring the difference performance. It is the act of running a simultaneous experiment between two or more variants. However, if you have more than 3 elements then it would be useful to learn about multiple variable tests.
 
Assumptions of AB Testing

1. Normality Assumption is means that you should make sure your data roughly fits a bell curve shape before running certain statistical tests or regression. 
	Using a Graph for a Normality Test
		1.1 Q-Q plot
		1.2 Box Plot
		1.3 Normal Probability Plot
		1.4 Histogram

	Statistical Tests for Normality
		1.1 Chi-square normality test.
		1.2 D’Agostino-Pearson Test
		1.3 Jarque-Bera Test
		1.4 Jarque-Bera Test
		1.5 Lilliefors Test
		1.6 Shapiro-Wilk Test ( In this script we will use this.)
		
# H0: Accept Ho (Normal Distribution) (No significant difference between the two groups mean values)
# H1: Reject Ho (Non-Normal Distribution)

p-value < 0.05 reject H0
p-value > 0.05 accept H0
		
2. Homogeneity of Variance analysis is used to test the hypothesis about whether there is a difference between two or more means.
		2.1 Hartley’s Fmax test 
		2.2 Cochran’s test 
		2.3 Levene’s test ( In this script we will use this.)
		2.4 Barlett’s test
		2.5 Brown-Forsythe Test
		
# H0: Accept Ho (variances are homogeneous) (No significant difference between the two groups variance values)
# H1: Reject Ho (variances are not homogeneous)		

p-value < 0.05 reject H0
p-value > 0.05 accept H0

Number of Dependent Variable = 1 and Number of Independent Variable = 1 => One Way ANOVA
Number of Dependent Variable = 1 and Number of Independent Variable = 2 => Two Way ANOVA

Number of Dependent Variable > 1 and Number of Independent Variable = 1 => One Way MANOVA
Number of Dependent Variable > 1 and Number of Independent Variable > 1 => Two Way MANOVA

* If the normality assumption is not fulfill the condition then non parametric methods are used. If it is nonparametric, we use the Mann Whitney u test instead of the AB test.

* If the homogeneity of variance assumption is not fulfill the condition then non parametric or parametric methods can be used. It is not as strict as the normality assumption.
We only need to make the equal_var parameter, which is one of the t_test parameters, to False if it is not homogeneous.

Let's get to know the data columns.

Impression : A link URL records an impression when it appears in a search result for a user.
Websit Click : When the user clicks on the website link in the ad
Search : When the user searches the website
View Content : When a user views details of a product
Add to cart : When a user adds a product to the basket.
Purchase : When a user purchases a porudct

We will apply AB test by dividing the population into two groups. First group : Control group. Second group : Test group.

Facebook ad with "maximum bidding" campaign is presented to "Control Group"
Another campaign with "average bidding" It is submitted to the "Test Group".

Success criterion is the Purchase variable.
