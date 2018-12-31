# Udacity - Data Visualization project: Performance of US flights

## Summary
Carrier, NAS (National Aviation Services), and Late Aircraft Delays cause most of the total delays in US air traffic (at least in the time period covered, i.e. 2004-2008). Surprisingly, weather accounts for a much smaller share of total delays, and security delays represent a tiny portion. There is systematic seasonal variation in delays, with summer months being particularly prone to delays, but there is also some variation in seasonal patterns across years. As airlines can do little to mitigate delays imposed by NAS (as well as weather issues), measures to improve flight performance should focus on carrier delays (which are due to e.g. maintenance or crew problems, aircraft cleaning, baggage loading, fueling, etc.) and in particular late aircraft delays, as delayed aircraft scheduled for upcoming flights will cause further delays (i.e. a compound effect).

For definitions of delays, see: 
https://www.bts.gov/topics/airlines-and-airports/airline-time-performance-and-causes-flight-delays

## Design
I selected the flights data from the data set options. I started with the most recent complete year available (i.e., 2008) from http://stat-computing.org/dataexpo/2009/the-data.html. I decided to show variations in flight performance patterns over time, i.e. seasonal variation, and distinguish between types of delays. Initially, I suspected that weather delays would account for a very large share of delays, and that those would vary significantly across seasons. However, it turned out that other delay types are much more prominent, specifically CarrierDelay, NASDelays, and in particular LateAircraftDelay. 

I decided to implement my project (primarily) in dimple.js, as D3 has a somewhat steeper learning curve and I'm not too familiar with the library (yet!). To gradually improve the chart across iterations, I asked 3 friends for feedback (labeled Reviewers 1-3). Their comments are documented below in the Feedback section. I incorporated the suggestions in my iterations toward the final chart.

As I wanted to show variation in types of delays over time, I decided on a line plot as the most suitable chart type, given that there is an inherent dependency on previous time points and the fact that time has a natural ordering. To allow for easy comparison across delay types, I included all types in a single plot (i.e., a multiple line plot). The lines are distinguished by color hue, which makes identification and labeling via a legend simple and easy to process for viewers. 

I first aggregated the data on a weekly basis. I ultimately changed this to a monthly aggregation based on feedback (see Reviewer 1). I also added points to the lines (i.e., double encoding) to help identify the actual data points and to highlight the fact that the data is aggregated (i.e., we are comparing monthly totals) based on feedback. 

Reviewer 2 suggested to consider changing the measure from an absolute to a relative measure, i.e. dividing total delay time by flights per month. I ultimately decided against this as a) there is actually fairly little variation in number of total flights per month across a given year and b) keeping the absolute measure was deemed more intuitive as the relative measure would require an understanding of the measure and knowledge of total flights per time period. 

Lastly, Reviewer 3 suggested adding data from other years to allow for further comparison. I ultimately included data from 2004 - 2008, the years where complete data was available with information on delay types. The final chart includes two types of interaction, enhancing understanding of the data. First, a tooltip appears with information on the particular data point when the user hovers over a given point. Second, users can transition between different years (2004-2008) through the select dropdown menu in the top left corner of the page.

**Update**
I made several changes to the visualization in light of reviewer comments. In order to make the visualization more explanatory, I focused on the surprising fact that weather only acccounts for a small share of delays as the core finding. In order to draw viewer attention to this, I changed the title and added a narrative paragraph explaining the data and the main finding. In addition, the line for weather now interactively first increases its stroke weight (using a transition), then shrinks back but maintains a slightly higher stroke weight when it is first rendered to draw attention to the comparatively low level for weather delays. When the viewer moves through different years, the weather delay line still has a slightly higher stroke weight to focus user attention, but does not move through the transition anymore as viewer attention should already be established (and continuous transitions may make the visualization too busy and not aid comprehension and usability anymore). Now, index3.html represents the version initially submitted. The new version is now labeled 'index_final.html'.

## Feedback
- Reviewer 1: "Very intesting project. A line plot is definitely a good way to show this type of data. But maybe you want to also include points so that users can identify the actual data points. Also, the lines are very "busy". I think aggregating by month would be sufficient to show the main trends across time."
- Reviewer 2: "Nice project. I agree that aggregating by month is better, it is easier to see the main trends. Maybe you want to show relative numbers, i.e. delay time per month divided by number of flights in that month? Just an idea, especially if there is a large variation of number of scheduled flights from one month to the next."
- Reviewer 3: "This looks great, there is definitely a message, and it is easy to perceive. Do you have data for other years? Then you could show how this has evolved over time."

## Resources
- Murray, S. (2017). Interactive Data Visualization for the Web: An Introduction to Designing with D3. O'Reilly Media, Inc.
- Meeks, E. (2018). D3.js in Action: Data Visualization with JavaScript. Manning Publications.
