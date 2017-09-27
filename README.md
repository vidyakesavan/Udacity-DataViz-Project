
# Udacity Data Analyst Nanodegree 
## Data Visualisation with D3.js

## Summary

Cellular communication has become an integral part of our life now. Less than two decades ago, cellular communication was unknown to most of the world. This chart shows the growth in cellular subscribers around the world from 1979 to 2014.

## Design
#### Choice of visualisation

The intent of my visualisation is to show:
- The growth in number of cellular subscribers from 1979 to 2014
- The difference in adoption rate among countries and continents

A  Choropleth map is a good way to show the change in subscribers over a period of time.

#### Data

The first version of this visual was built using Gapminder data on cellular subscribers. The data had some missing values for intermediate years. The missing values were represented as ‘0’ in the data and there was no easy way to differentiate a ‘0’ that is a missing value from a no cellular subscriber.

I added a footnote indicating that some countries contain missing values. Still, this was a confusing aspect for users and I received feedback wondering why Netherlands had zero subscribers in 2011.

As I was looking at ways to handle this issue, I found the cellular subscription data on UN website and this was complete with no missing records. This visualisation uses the UN data.

There were some discrepancies in country names between the world_countries JSON used to draw the map and the UN data. To address this, the country names in JSON are changed to matching country names from the data in the code. 

#### Narrative Structure

I wanted to use a Martini Glass Narrative structure for the visualisation. A martini glass narrative structure starts as an author-driven narrative and transitions to a viewer-driven narrative. This visual starts with an animation that iterates through the years and colours the map. At the end of the visual, the viewer is provided with a slider to move through freely between the years and use tooltips to investigate details.

The first version of the visual began the animation automatically on load. I understood through feedback that some users found this confusing, especially since the colours on the map are very mild at the start. Also, the animation starting off without warning did not give the user enough time to read the introductory text and get context on what to do once the animation stops.

#### Colors

The visual shows a sequential data in number of cellular subscribers across years. 

For the choropleth map I wanted to use a sequential colour scale that stands out against the colour of the water. The first colour scale I chose was shades of green. The feedback suggested that the colour, especially in its lightest was very hard to notice and the differences between threshold ranges are not easily seen. One feedback was that they had to use tooltips often to see which colour bucket a country fell in. So I changed the colour scale to Yellow-Orange-Brown (YlOrBr) from www.colorbrewer.org.

#### Tooltips

I wanted tooltips to provide information on the country, year and number of subscribers.
There are a handful of countries for which UN data does not contain data. These appear grey on the map. The tooltips for these countries showed NaN subscribers as they had no data. This was fixed in the final version to indicate data is not available for this country.

#### Legends

Legends are implemented using d3.legend.js from http://d3-legend.susielu.com/#color-threshold

I created custom legend in the first version of the visual, but I found the legend.js to be very versatile and easy to implement.


## Feedback



#### Feedback 1: Sophia Jose

What do you notice in the visualisation?

What questions do you have about the data?
> Places like Greenland show dark green. Is it also because of low density of population.?Is it average subscription for the country? Like India would ideally have different shades in cities and villages? So how helpful would this info be?  Like the subscription of a developed country like Canada and developing country like India has similar subscription in the visualisation.

What relationships do you notice:
> As years progressed the mobile penetration increased. The green darkened.

What do you think is the main takeaway from this visualization?
> Mobile penetration is on the rise. Continents like South America/ Europe  look almost saturated while Africa shows scope for more subscription. 

Is there something you don’t understand in the graphic?
> At first...it was little difficult to differentiate the shades..then on hover over the countries displayed the numbers which helped. Netherland showed 0 subscription??

#### Feedback 2: Murali Rangarajan

What do you notice in the visualisation?
> The viz uses a heat map to show how cellular subscription has risen over the years across the globe. The slider gives an idea as to who the early adopters were.

What questions do you have about the data?
> What would be interesting to know is the number of subscribers who had more than one connection. While the rise of subscriptions per 100 sheds some light on the adoption rate, it does not tell what the reach is. Another interesting data point would be the population growth rate of a country vis-a-vis the subscription growth rate.

What relationships do you notice?
> Developed nations are more likely to have adopted cellular communications technology earlier than developing nations. Mid 2000 years mark the rise of cellular communications in developing nations while it was already prevalent in European countries (and well entrenched in Scandinavian). However, by 2011, the late adopters seem to have soared well past the early adopters in terms of subscriptions per 100.

What do you think is the main takeaway from this visualization?
> It appears that while cellular technology was available as early as 1979, it took over two decades for world wide adoption. There seems to be an inflection point (around early 2000s) at which the technology really took off outside of Europe and North America. 

Is there something you don’t understand in the graphic?
> Visually, it is not very easy to differentiate between a 0 and a 30. An increase from 0 to 10 to 30 could be more obvious.

#### Feedback 3: Rabiya Ghouse

What do you notice in the visualisation?
> As soon as I load the visualisation, it slowly changes over time dimension, showing the cellular growth over time. It also gives me the ability to look at the growth in a particular year by using the time scale slider

What questions do you have about the data?
> Handling missing values in the data- could it be handled better.

What relationships do you notice?
> Initial growth in Scandinavian countries ( mostly attributed to them being mobile market leaders) and in developed countries. Canada despite starting early on, have a few countries over take mobile growth soon.

What do you think is the main takeaway from this visualization?
> does as says on the tin :)

Is there something you don’t understand in the graphic?
> sometimes 0 subscription is color coded light green for a few countries and no color for some?



## Resources

Colors
(http://colorbrewer2.org/#type=sequential&scheme=Greens&n=8)

Graticule
(https://gist.github.com/gdmf/4180596)

Legend
(http://d3-legend.susielu.com/#color-threshold)

Udacity forum (https://discussions.udacity.com/t/find-and-select-through-json/177759/10)

JSON countries to draw the map
(https://github.com/honcheng/world.geo.json/blob/ccbedc4c5b6bdb4949244adfc2915199d566ce71/countries.geo.json)

Sample Map
(http://bl.ocks.org/tomschulze/961d57bd1bbd2a9ef993f2e8645cb8d2)

Creating a gist
(https://discussions.udacity.com/t/p6-sharing-how-to-make-a-gist/43772)







