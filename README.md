# AB Testing

## Purpose
To apply AB testing to data obtained from [Kaggle](https://www.kaggle.com/datasets/ilkeryildiz/example-dataset-for-ab-test).

## Process

I loaded the data and performed EDA on both the Control and Test groups. The Control group had one row with nulls and I replaced them with the median value for that feature. I could have removed it and removed the matching day for the Test group, but I thought it would omit valuable information.

This was my first exposure to ecommerce data and I had to look up a few of the feature names and potential KPI's I could calculate - They may be incorrect, but I was focused more on the process of A/B testing than calculating KPI metrics.

After EDA, I joined the two datasets as I wanted to compare the groups over the testing window. I used the combined data to calculate the average measure for each feature and compare them to see if there was a difference. I compared the features over the testing window in the form of a lineplot so see the change over time.

I found the data was non-normal from EDA and had to apply non-parametric statistical tests.
The metrics (might not be the most accurate) I chose were as follows:
- Conversion Rate =  # of Purchase/ # Add to cart
- Click-through rate = # of website clicks / # of impressions
- Revenue per Day = total Spend[USD] / day
- View rate = # of view content / # of Searches 

I plotted these metrics for each group to visualize any differences. The statistical test I chose was the Mann-Whitney test as my data was non-normal. 

## Results

Feature Perspective:
- The Control group outperformed the Test group in the following features:
    - Impressions, Reach, Views, Add to Cart
- The Test group outperformed the Control group in the following features:
    - Spend [USD], Website clicks, Searches
- Puchases was practically identical

KPI Persepective:
- The Control group outperformed the Test Group in the following metrics:
    - View Rate
- The Test group outperformed the Control group in the following features:
    - Conversion Rate, Click-Through rate, Revenue per day

A/B Testing:

The hypothesis tests using Mann-Whitney indicated the differences were statistically significant for the chosen KPI metrics. 

## Conclusion
The Test group was superior to the Control group and overall better at generating monetary value than the Control group. The Control group did have a better view rate, but could not convert those to sales which is what we are ultimately interested in 