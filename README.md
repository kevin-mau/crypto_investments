# *Crypto Investments*
---
In this application, we’ll use machine unsupervised learning to evaluate cryptocurrency price change history.
We will create a Jupyter notebook that clusters cryptocurrencies by their performance in different time periods
and use plot visualizations to study the results.

The CSV file that’s stored in the Resources folder contains the price change data of cryptocurrencies in 
different periods.  Analysis will be done using the jupyter notebook, Python Pandas, and scikit-learn.  We will also 
use hvplot to create interactive visualizations.  

---
## Technologies:

The Jupyter file utilizes python 3.7 along with the following libraries:

pandas

hvplot.pandas

scikit-learn

pathlib

```python
  pip install jupyterlab
  pip install pandas
  conda install -c pyviz hvplot 
  pip install -U scikit-learn
```

## Usage:
In the jupyter notebook, we begin by loading in the price change percentages data of the cryptocurrencies.
```python
  df_market_data = pd.read_csv(
    Path("Resources/crypto_market_data.csv"),
    index_col="coin_id")
```

We will create a dataframe from the CSV data which we will use for analysis.  Here is a visualization of the dataframe:
![crypto_data](https://github.com/kevin-mau/crypto_investments/blob/main/Resources/crypto_data.png?raw=true)

Using standard scaler we will standardize the data so that we can apply machine learning.
```python
  scaled_data = StandardScaler().fit_transform(df_market_data)
```

In order to find the best value for k value we will fit the model to the data using a range from 1 to 11 and append the model.inertia_ to the inertia list.
```python
for i in k:
    k_model = KMeans(n_clusters=i, random_state=1)
    k_model.fit(df_market_data_scaled)
    inertia.append(k_model.inertia_)
```
With the best value for k, we will create and predict the clusters to group the cryptocurrencies using the scaled data.
```python
    model = KMeans(n_clusters=4, random_state=4)
    model.fit(df_market_data_scaled)
    k_4 = model.predict(df_market_data_scaled)
```    

We will move on to optimize clusters with Principal Component Analysis.  To create a PCA model instance :
```python
    pca=PCA(n_components=3)
    market_data_pca = pca.fit_transform(df_market_data_scaled)
``` 

With the PCA model, we can apply the also create the elbow curve and finding k, and also create scatter plots.

We will create the interactive plots and put them side-by-side for visual comparison:
![elbow_curves](https://github.com/kevin-mau/crypto_investments/blob/main/Resources/elbow_curves.png?raw=true)
![scatter_plots](https://github.com/kevin-mau/crypto_investments/blob/main/Resources/scatter_plots.png?raw=true)


## Data:

The crypto_market_data.csv file is a CSV file that is data of 41 different cryptocurrencies and their price change
percentages for different time periods ranging from 24 hours to 1 year.

---

## Contributors

kevin-mau

---

## License

MIT
