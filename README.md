# Udacity - Data Visualization project: Performance of US flights

## Summary
Carrier, NAS (National Aviation Services), and Late Aircraft Delays cause most of the total delays in US air traffic. Surprisingly, weather accounts for a much smaller share of total delays, and security delays represent a tiny portion. There is systematic seasonal variation in delays, with summer months being particularly prone to delays, but there is also substantial variation across years. As airlines can do little to mitigate delays imposed by NAS, measures to improve flight performance should focus on carrier delays (due to e.g. maintenance or crew problems, aircraft cleaning, baggage loading, fueling, etc.) and in particular late aircraft delays, as delayed aircraft scheduled for upcoming flights will cause further delays (i.e. a compound effect).

For definitions of delays, see: 
https://www.bts.gov/topics/airlines-and-airports/airline-time-performance-and-causes-flight-delays
## Design
I selected the flights data from the data set options. I started with the most recent complete year available (i.e., 2008) from http://stat-computing.org/dataexpo/2009/the-data.html. I decided to show variations in flight performance patterns over time, i.e. seasonal variation. Initially, I suspected that weather delays would account for a very large share of delays, and that those would vary significantly across seasons. However, it turned out that other delay types are much more prominent, specifically CarrierDelay, NASDelays, and in particular LateAircraftDelay. 

As I wanted to show variation in types of delays over time, I decided on a line plot as the most suitable chart type, given that there is an inherent dependency on previous time points and time has a natural ordering. To allow for easy comparison across delay types, I included all types in a single plot (i.e., a multiple line plot). The lines are distinguished by color hue, which makes identification and labeling via a legend simple and easy to process for viewers. 

I first aggregated the data on a weekly basis. I ultimately changed this to a monthly aggregation based on feedback (see Reviewer 1). I also added points to the lines (i.e., double encoding) to help identify the actual data points and to highlight the fact that the data is aggregated (i.e., we are comparing monthly totals) based on feedback. 

Reviewer 2 suggested to consider changing the measure from absolute to a relative measure, i.e. dividing total delay time by flights per month. I ultimately decided against this as a) there is actually fairly little variation in number of total flights per month across a given year and b) keeping the absolute measure was deemed more intuitive as the relative measure would require an understanding of the measure and knowledge of total flights per time period. 

Lastly, Reviewer 3 suggested adding data from other years to allow for further comparison. I ultimately included data from 2004 - 2008, the years where complete data was available with information on delay types. The final chart then includes two types of interaction. First, there a tooltip appears with information on the particular data point when the user hovers over a given point. Second, users can transition between different years (2004-2008) through the select dropdown menu in the top left corner of the page. 

## Feedback

## Resources
- Murray, S. (2017). Interactive Data Visualization for the Web: An Introduction to Designing with D3. O'Reilly Media, Inc.
- Meeks, E. (2018). D3.js in Action: Data Visualization with JavaScript. Manning Publications.
