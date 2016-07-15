# INFO5100 Data Visualization Project3: Airbnb Belong to Anywhere

## Introduction

Founded in August 2008, Airbnb, matches hosts that are looking to monetize their extra
space, with guests that are looking to find unique accommodations. Co-founders
Chesky and Gebbia, accommodated three guests on air mattresses and provided
homemade breakfast, in order to help afford the rent for their loft in San Francisco.
It is now a thriving business model providing host-and-guest match across 34000 cities 
in 191 countries based on a peer-to-peer business-social network

For this peer-to-peer accommodation market place to work, Airbnb encourages the
hosts to build their online profile and promote their hosting philosophies. Guests choose
their accommodation based on published reviews, and are encouraged to leave a
review themselves. Such reviews build validity and references, both for the guests and
the host, and forms a cyclic and self sustaining business model

As part of our project, we wanted to gain a deeper understanding of the cyclic review
and pricing model of Airbnb rental listings, and analyze how host registration have fared
over the years, which are the popular property types chosen by guests and how the
monetary and referential responses feed back into the Airbnb system

## Data
### Source

Our data source is “Inside Airbnb”, an independent, non-commercial, open source data
tool funded personally by Murray Cox. By using public available information, Inside
Airbnb provides data based on 50+ data points for each listing

[http://insideairbnb.com/get-the-data.html](http://insideairbnb.com/get-the-data.html)
### Dataset: Fetching, Cleaning and Transforming data
From insideairbnb.com, we selected eight major cities in the United States. The dataset
for each of these cities contained multiple columns with information for different fields.
Based on our project, we selected only those that were relevant to us. In the final
cleaned-up version of the dataset, we retained the following fields:

• host_since: The date on which the host registered with Airbnb
• property_type: Includes a variety of listings like apartments, houses, lofts & etc
• room_type: Involves 3 sub-types namely private room, shared room, entire
house/apt
• price: Price per day of the rental listing
• number_of_reviews: The total number of reviews that the listing received
• review_scores_rating: The rating/score of the listing
• review_per_month: The average number of reviews received by the listing in a
month

## Telling our Story – Mapping data to visual elements

Touted as one of the next-generation multibillion-dollar startup, Airbnb boasts of a
sustainable peer-to-peer business model, where it enables transactions between two
entities by charging a 'service fee' without directly owning any rooms by itself. Unlike
traditional business models that aim for scalability by building on their own resources in
limited space and sky-rocketing prices, Airbnb adopts a strategic business model by
increasing the interactions between people, and cashing in on a quasi business-social
network

### Variables & Visualizations
**Visualization 1: Hosts’ Standards**

Our visualization tells the story of Airbnb, from the days of its inception until 2015. We
look at the unusual and innovative business model brought about by Airbnb, starting
from the review and pricing models, how different Airbnbs fare in terms of reviews, and
how these listings feed back into the system by generating more even more reviews

Measured across eight major cities in the US, the first of our visualizations shows the
value of a host in terms of the review and pricing models that forms the core of Airbnb’s
successful business model- number of reviews received by a host, the review score and
the price range of the listings

Use the sliders to adjust the hosts’ standards scale - number of reviews received by a
host, the review score and the price range of the rental listings. With the “Current Hosts
(Number)” selected, the bar graph shows the number of hosts that satisfy these
standards. The “Current Hosts (Percentage)” option, on the other hand, shows the % of
the total number of hosts that satisfy these conditions

Click on each bar to see the percentage distribution of the types of properties available
in each city, and the percentage distribution of the types of rooms available in each of
these properties, and the number of hosts that registered with Airbnb from the the early
days until 2015

**updateScale**: In this function, we update the scale of the bar chart according to the
selection range in the sliders. Here, we calculate the total number of hosts that match
the condition set by the slider in each city. Then, we put this data in a global variable
called result. The min and max values of result, then forms the min and max values for
the linear scale of the bar chart

**drawLabel**: This function is called once to create the city label besides the bar chart
createList: This function is called to create the bar chart
updateList: In this function, we update the bar chart according to the values selected in
the slider

**updateListPercentage**: Called when the “Current Hosts(Percentage) button is clicked

**Colors for the visualization:**

The color for the bar chart is based on “red” with a gradient opacity
The color for the slider is set in the jquery.nstSlider.css

**Visualization 2: Your Home Everywhere**

From air mattresses in 2008, Airbnb has gone on to expand the type of its listings, and
now lists a variety of properties including entire homes and apartments, private rooms,
castles, boats, private islands among others. The visualizations below bring out the
richness of this variety, while shows how more and more hosts are adopting Airbnb to
monetize their extra space

Click on each slice of the pie chart, to explore the details as a function of the number of
reviews per month and the prices per day ($)

The pieData function is to clean up and parse data for the pie charts. There are three
pie charts and we want to get the number and percentage of categories of each of the
three pies. So the function scans the dataset of a given city, classifies data and then
builds arrays for the drawPie function

The drawPie function is to draw the pie charts themselves and takes in the array of data
built from pieData. It also takes in id, which denotes where the pie should be drawn, and
data, which is to pass by data for the spot chart in step three. When hovering over the
regions/slices on the pies, users could view the exact number and percentage of the
interested region. In addition, we made each region on the pies clickable, which leads
the users to step three

### Visualization 3: Thriving Business Model That Feeds Itself

What started as an air mattress renting necessitated by need, Airbnb now boasts of a
thriving business model providing host-and-guest match across 34000 cities in 191
countries. It does so by enabling transactions between two entities and charging a
'service fee' without directly owning any rooms by itself. Such a model builds and feeds
itself by maintaining a fine balance between the reviews attained and the costs quoted.
The third of our visualizations shows how reviews and costs are distributed according to
various parameters on the pie chart above

In the spot chart, we mapped each entry in the dataset as a circle on the graph. The x
axis means the price of the listing per day and the y axis represents the number of
reviews the listing receives per month. Both the x and y axis can adjust automatically
according to maximum and minimum number of the entries

The colors denote the review scores. While blue means a fairly low score, red indicates
nearly full score. As most of the listings have scores above 80, we set the color range
from 80 to 90 as progressing from light green to light orange, for the range from 90 to
100, we set the color range from light orange to red. This ensures a more visible color
change between subtle difference

The spotData function is to draw the spot graph. It takes in data passed by the drawPie
function and uses it to map every entry

## Lessons from the data visualization

The popularity of Airbnb is increasing year over year, as seen from the second
visualization. The number of hosts signing up with Airbnb is a good indicator of how
people are responsive to business models that are out of the norm

Even though Airbnb boasts of a variety of property listings, the most common and
popular ones are not destination homes. Rather, they are regular apartments or houses
that serve the needs of Airbnb guests in a more practical manner

As seen from our third visualization. most of the spots are in the lower left corner. This
means that low priced listings have a bigger chance to receive more reviews, andmay
become popular more easily than high priced, exclusive rental listings

## References

1. [A jQuery library for the range sliders](https://github.com/lokku/jquery-nstslider)

2. Bootstrap grid to help make the project responsive.
