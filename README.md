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
