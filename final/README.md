# Important Links
## Examples of Ordinal Logistic Regressions in R
https://stats.idre.ucla.edu/r/dae/ordinal-logistic-regression/
http://data.princeton.edu/wws509/R/c6s2.html
http://mc-stan.org/rstanarm/articles/polr.html

## Documentation in STAN for ordinal regression models
In stan Ref version 2.17, checkout sections: 
* 9.6. Multi-Logit Regression 
* 9.9. Hierarchical Logistic Regression
https://github.com/stan-dev/stan/releases/download/v2.17.0/stan-reference-2.17.0.pdf

Here is rstanarm package that fits STAN inside R:
http://mc-stan.org/rstanarm/reference/stan_polr.html
http://mc-stan.org/rstanarm/articles/polr.html


Q&A online:
https://stats.stackexchange.com/questions/226070/stan-multilevel-ordinal-logistic-regression
https://groups.google.com/forum/#!category-topic/stan-users/general/sgX2Edo8qiQ
http://discourse.mc-stan.org/t/multi-level-ordered-logistic-regression-where-to-put-the-varying-part-of-the-model/996


## Education research using STAN
https://education-stan.github.io/



## Data
https://www.kaggle.com/aljarah/xAPI-Edu-Data/home


## Run jupyter notebook on server side:
On the server side:
```
 # configure jupyter and prompt for password
 jupyter notebook --generate-config
 jupass=`python -c "from notebook.auth import passwd; print(passwd())"`
 echo "c.NotebookApp.password = u'"$jupass"'" >> $HOME/.jupyter/jupyter_notebook_config.py
 echo "c.NotebookApp.ip = '*'" >> $HOME/.jupyter/jupyter_notebook_config.py
 echo "c.NotebookApp.open_browser = False" >>  $HOME/.jupyter/jupyter_notebook_config.py 
```

On the client side:
```
```
