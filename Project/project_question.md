# Project Question

## Predicting government health spending
US govt expenditure on healthcare is set to reach 20 % of GDP by 2025. There are many contributing factors, but is there some way to target efforts to reduce spending?<sup>1</sup>


##what is the question you hope to answer?
Can we predict the payment from Centers to Medicare and Medicaid (CMS) for a county based on service type and county demographics?

##corollary questions

1. What are risk factors or for increased government health spending?
2. What sectors of USA society (in terms of demographics) are most poorly served? i.e. for where and who are health expenditure the greatest? 
3. Where is the least amount of money spent?
4. Are there demographic differences between where the most amount of money is spent and the least?

##what data are you planning to use to answer that question?

1. CMS payment information for 2011-2014 for outpatient services for healthcare spending information <sup>2</sup>
2. USA census American Communities Survey 2011-2014 for demographic data <sup>3</sup>

##What do you know about the data so far?
The healthcare spending dataset is spelled out by provider by service by zipcode and can be rolled up to the level of county via zip code. This data set is relatively small, 1.7 Mb zip file.
The ACS data set has a lot of dimensions (62720) that will need to be pared down. It has to be accessed via API.

##why did you choose this project?
I work in the healthcare industry and I'm interested in healthcare questions. Government spending on healthcare in the US is one indicator of the on going struggles the US healthcare system faces. Attempting to understand some drivers and impacts of that spending .

###References

1. [Sean P. Keehan, John A. Poisal, Gigi A. Cuckler, Andrea M. Sisko, Sheila D. Smith, Andrew J. Madison, Devin A. Stone, Christian J. Wolfe, and Joseph M. Lizonitz _National Health Expenditure Projections, 2015–25: Economy, Prices, And Aging Expected To Shape Spending And Enrollment_ Health Affairs Vol 35 No. 7](http://content.healthaffairs.org/content/early/2016/07/15/hlthaff.2016.0459)
2. [Medicare Provider Utilization and Payment Data: Outpatient](https://www.cms.gov/research-statistics-data-and-systems/statistics-trends-and-reports/medicare-provider-charge-data/outpatient.html)
3. [American Community Survey 1 Year Data (2014, 2013, 2012, 2011)](https://www.census.gov/data/developers/data-sets/acs-survey-1-year-data.html)
