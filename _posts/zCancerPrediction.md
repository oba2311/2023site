---
# title: Predicting Breast Cancer
layout: page
description: "Predicting Breast Cancer with Binary Classification"
image: assets/images/1.png
nav-menu: true
---

<!-- Main -->
<div id="main">

<!-- One -->
<section id="one">
	<div class="inner">
		<header class="major">
			<h2>Predicting Breast Cancer - Binary Classification </h2>
		</header>
I chose to work with the Wisconsin breast cancer dataset. The question at hand is:
<br>
<i>Which characteristics can help accurately predict whether a tumor is a benign one or malignant?</i> 
<br>
<br>

This is an important question since if such characteristics can be found having much predictive power, potentially malignant tumors could be identified earlier and lives will be saved. This is not a truly causal question, since the shape or size of the tumor does not cause it to be malignant, but rather could be highly correlated; therefore, it is more of a descriptive question. For true causal inference, matching or for some treatment should be calculated. Classification tasks such as this one are good to gauge a descriptive understanding.
<br>
<br>
<b>The Model:</b>
<br>
The target variable is the observation — malignant or benign. Class distribution: 357 benign, 212 malignant
Since this is a case-study classic dataset I didn’t need to transform any variable. While numerous variables exist, and there could be a whole study regarding feature selection based on this data, since our focus is on the model specification and not feature selection I will choose only one variable (“Cell.size”) to shed light on model differences.
<br>
<br>

<ul class="actions">
	<li><a href="http://rpubs.com/oba2311/binary-classification-breast-cancer" class="button">R code</a></li>
			</ul>
				</div>
</section>

<!-- Two -->
<section id="two" class="spotlights">
	<section>
	</section>
	<section>
		<a class="image">
			<img src="{% link assets/images/logit.png %}" alt="" data-position="top center" />
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>Logit Model:</h3>
				</header>
				<p>We see that Cell.size, which represents the uniformity of the cell size, is used in the logit model such that patients with size that is classified higher than 4 are likely to have malignant tumor.</p>
			</div>
		</div>
	</section>

<section>
	<a class="image">
		<img src="{% link assets/images/probit.png %}" alt="" data-position="25% 25%" />
	</a>
	<div class="content">
		<div class="inner">
			<header class="major">
				<h3>Probit Model:</h3>
			</header>
			<p>We see that as observed by other models, Cell Size of over ~3.75 is correlated with over 50% risk of malignant tumor. Lastly, let’s add confidence intervals and jitter to the classes, and use the LOWESS so we can see the mass of the data against the predictor:​</p>
		</div>
	</div>
</section>

<section>
		<a class="image">
			<img src="{% link assets/images/1.png %}" alt="" data-position="top center" />
		</a>
		<div class="content">
			<div class="inner">
				<header class="major">
					<h3>LOWESS - LOcally WEighted Scaterplot Smoothing:</h3>
				</header>
				<p>We see that as our model predicted, the Cell size indeed encapsulates a lot of the classes characteristic. Much more experimentation can, and should be done in order to prove this correlation; nevertheless, this analysis shows that the cell size is an important predictor when diagnosing tumors.</p>
			</div>
		</div>
	</section>