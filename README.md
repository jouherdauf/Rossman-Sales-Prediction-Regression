	  
<h1>Retail-Sales-Prediction</h1>


<p>Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied. My work includes various plots and graphs , visualizations , feature engineering , ensemble techniques , different ML algorithms with their respective parameter tuning , analysis and trends . Predictions are of 6 weeks of daily sales for 1,115 stores located across Germany.

In this project, the Kaggle Rossman challenge is being taken on. The goal is to predict the Sales of a given store on a given day. Model performance is evaluated on the root mean absolute percentage error (MAPE).


The dataset consists of two csv files: store.csv and train.csv

Data Files:

train.csv holds info about each store. store.csv holds the sales info per day for each store.

The repo contains main.py that runs the main script from step one until the end.</p>


<h3>1. Business Problem.</h3>
<p>Rossmann operates over 3,000 drug stores in 7 European countries. Currently, Rossmann store managers are tasked with predicting their daily sales for up to six weeks in advance. Store sales are influenced by many factors, including promotions, competition, school and state holidays, seasonality, and locality. With thousands of individual managers predicting sales based on their unique circumstances, the accuracy of results can be quite varied.</p>

<h3>2. Solution Strategy</h3>
<p>My strategy to solve this challenge was:</p>
<ol type= 1>
<li>Data Description: Use statistics metrics to identify data distributions.</li>

<li>Feature Engineering: Derive new attributes based on the original variables to better describe the phenomenon that will be modeled.</li>

<li>Exploratory Data Analysis: Explore the data to find insights and better understand the impact of variables on model learning.</li>

<li>Feature Selection: Selection of the most significant attributes for training the model.</li>

<li>Machine Learning Modelling: Machine Learning model training.</li>

<li>Hyperparameter Fine Tunning: hoose the best values for each of the parameters of the model selected from the previous step.</li>

<li>Convert Model Performance to Business Values: Convert the performance of the Machine Learning model into a business result.</li>
</ol>

 <h3>3.Machine Learning Model Implementation and performance</h3>
<p>At this stage models used : *Linear Regression, *Lasso Regression, *Random Forest Regressor</p>
<table >
	<tr >	
		<th>Regression Model</th>
		<th>Train MSE</th>
		<th>Train RMSE</th>
		<th>Train R2</th>
		<th>Train Adjusted_R2</th>
		<th>Test MSE</th>
		<th>Test RMSE</th>
		<th>Test R2</th>
		<th>Test Adjusted R2</th>
	</tr>
	<tr>								
		<td>Linear Regression</td>
		<td>1.214859e+06</td>
		<td>1102.206527</td>
		<td>0.844978</td>
		<td>0.844975</td>
		<td>1.217627e+06</td>
		<td>1103.461202</td>
		<td>0.844943</td>
		<td>0.844929</td>
	</tr>
        <tr>								
		<td>Lasso Regression</td>
		<td>1.214485e+06</td>
		<td>1102.036953</td>
		<td>0.845026</td>
		<td>0.845012</td>
		<td>1.217348e+06</td>
		<td>1103.334986</td>
		<td>0.844979</td>
		<td>0.844965</td>
	</tr>
	<tr>							
		<td>Ridge Regression</td>
		<td>1.214486e+06</td>
		<td>1102.037084</td>
		<td>0.845026</td>
		<td>0.845022</td>
		<td>1.217348e+06</td>
		<td>1103.335147</td>
		<td>0.844979</td>
		<td>0.844965</td>
	</tr>
	<tr>								
		<td>Elastic Net Regression</td>
		<td>1.214485e+06</td>
		<td>1102.036949</td>
		<td>0.845026</td>
		<td>0.845022</td>
		<td>1.217348e+06</td>
		<td>1103.334982</td>
		<td>0.844979</td>
		<td>0.844965</td>
	</tr>
	<tr>
		<td>Decsion Tree Regression</td>							
		<td>1.362364e+06</td>
		<td>1167.203328</td>
		<td>0.826156</td>
		<td>0.826152</td>
		<td>1.367349e+06</td>
		<td>1169.337164</td>
		<td>0.825877</td>
		<td>0.825861</td>
	</tr>
	<tr>							
		<td>Random Forest Regression</td>
		<td>5.596015e+04</td>
		<td>236.558981</td>
		<td>0.992859</td>
		<td>0.992859</td>
		<td>3.200686e+05</td>
		<td>565.746016</td>
		<td>0.959241</td>
		<td>0.959238</td>
	</tr>
</table>






<h3>4. Conclusion</h3>

### **Conclusions from Modelling**
<ol type = '1'>
<li>The linear regression  model is least accurate as it has very high coefficient of Assortment categories </br>and Store type categories and it neglected features like customers,promotions which has positive</br> correlation with sales,so we have use hyperparameter tuning to impose penalties on coefficients.</li>
<li>Decision Tree Model  density distribution plot of sales varies highly with real data of sales.</li>
<li>Random Forest Regression has 99% accuracy for train data but 96% for test data, so this type of</br> model cant be trusted,as the difference between train
-test is very high</li>
<li>The most accurate models are Ridge,Lasso and Elastic-Net Regression,there train-test performances are</br> almost similar and coefficient's are also similar.</li>
<li>The week of year lineplot shows that Predicted Sales follows  Actual Sales,with varaition of mostly 700 </br>dollars,except for last 2 week of the year</li>
</ol>
