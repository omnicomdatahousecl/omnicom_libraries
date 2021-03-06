# Marketing Science | Omnicom media group | Comscore Library

Developed by the Omnicom Marketing Science team

## Introduction

Comscore is a platform that allows us to know a little more about the behavior of users within the internet.

Thanks to the help of the annalect teams, we have all the information available in our databases.

For this reason, we generate a module that allows consulting the data without having to know SQL.

You can run the different modules of the package through the following link: https://colab.research.google.com/drive/1DAQus4KWhL38OQeTMGLpCACMcmHi99Z9?usp=sharing

However, if you know about python, this package allows you to further customize and standardize your queries, creating programs that execute them periodically.

``` python

pip install pycomscore

from pycomscore import comscore_omnicom_database
coms_obj = comscore_omnicom_database(user = 'user', password = 'pass')

```

Here are some examples of the first methods.

``` python

dataframe_geo = coms_obj.demographics_by_web(country = 'mx', start_date = '2020-01-01', end_date = '2020-12-31', 
                                            event_like = 'atv', 
                                            domain = 'brp.com', 
                                            saved = False, 
                                            age_group = True,
                                            ages_between = None, gender_between = None)
dataframe_geo.head(15)

# countries ['us','ar', 'au','br', 'ca', 'cl', 'co', 'hk', 'id', 'in', 'mx', 'my', 'nz', 'sg', 'tw']
```

``` python
all_probabilities, short_frame_probabilities = coms_obj.bayesian_inference_over_sites(country = 'cl', 
                                                                                      domain = 'sodimac.cl', 
                                                                                      time_spent = 300, 
                                                                                      start_date = '2021-01-01',
                                                                                      end_date ='2021-05-01')
short_frame_probabilities.head(15)

```

If you have any advice, you can write to our team via email at data.analitica@omnicommediagroup.com