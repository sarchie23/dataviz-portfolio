# Critique By Design 2

## Step one: the visualization
The World’s 50 Largest Cities, From 1975 to 2050 ([Link](https://www.visualcapitalist.com/ranked-the-worlds-50-largest-cities-from-1975-to-2050/))
<img width="1500" height="812" alt="image" src="https://github.com/user-attachments/assets/96fb5c92-c4c4-41f9-8899-07429eb8d30e" />

I chose this visualization because I found the material interesting but presented poorly. 

## Step two: the critique
The information presented is not complicated to understand; this is information that the general public knows. But by presenting it as a series of 50 x 4 bubble charts with flags and a callout number on the side in a semi-circle around a globe with 10 points, it is a lot to digest. The message of what to take away is not clear. It is hard to read with small font. Knowing the underlying trends from my own prior work and academic experience as well as from investigating this image and its data for a few hours, I thought I could simplify the graphic and convey most of the information it attempted to present.

## Step three: Sketch a solution
I started out thinking about making a sankey diagram or bump chart that would show country population ranks during the visualization time period (1975 - 2025), as shown in the sketch below.
<img width="1956" height="844" alt="image" src="https://github.com/user-attachments/assets/3dea4e57-389c-4bb8-84ed-4d4c1dff6d48" />

The data linked to the visualization had 4 time periods for the top 50 cities in 2050. I initially used that to try to generate some graphs but quickly realized that the data was incomplete. The list only included the top 50 cities in 2050 (projected) and their populations during the time periods. But those cities are not necessarily the top 50 cities for the previous three time periods. So then I went to the data source for the visualization and gathered the top 50 cities at all of the four time points and then tried to make a sankey/bump chart but that got very messy very quickly because there are many cities that enter and exit the list during the different time periods. An example of a bump chart looking at the top 10 cities in each time period is shown below. Note: the highest rank (1) is at the bottom of the chart (I would reverse this if I was to keep going forward with this design).
<img width="1327" height="770" alt="image" src="https://github.com/user-attachments/assets/09bdd0fe-7a44-47a6-b210-daa228cf10d2" />

Then I thought I would try keeping the top 30 from the 2050 projections and just show those countries going back in time, which is shown in the image below. Note: the highest rank (1) is at the bottom of the chart (I would reverse this if I was to keep going forward with this design).
<img width="1330" height="747" alt="image" src="https://github.com/user-attachments/assets/9a9022b3-42a1-4895-a568-534f3a5de4f4" />

That made me realize another issue: how to classify regions. This [article](https://ourworldindata.org/world-region-map-definitions) helped me think through some potential options because I wanted there to be some meaningful groupings, especially for Asia, which compromised a lot of the cities. I tried split up the major continents into meaningful sub-groups where appropriate and then use different hues of the same color for those continents. I got very bogged down in which one to use and they all left me feeling frustrated and I still think the bump chart was more difficult to interpret even if I got the groupings right. 

I tried another type of visualization, the tree chart, which is shown below. I added a time component, so it could cycle through different time periods. But that didn't capture the change over the entire period well, in my opinion, which was a key component of the initial visualization.
<img width="1166" height="784" alt="image" src="https://github.com/user-attachments/assets/26855090-e966-4d98-8e2b-9f555528e07d" />

I then tried to do a bubble chart, taking a part of the initial visualization that I liked but presenting it linearly rather than in a semi-circle. I still ran into the region issue and I it was too large to fit on my 15" screen which I thought was a problem. 
<img width="513" height="774" alt="image" src="https://github.com/user-attachments/assets/1c9b6257-c434-4bf0-8e3a-1ce07a8a7060" />

Then I landed on my best solution to this point, which was a map, which is shown below. The map had the top 50 cities in 2050 with bubbles representing population size and the color representing change in population from 1975-2025. I also included a 2050 rank label. 
<img width="1560" height="784" alt="image" src="https://github.com/user-attachments/assets/e4c35b64-e7e1-4e37-b793-051c4ca19cc2" />

## Step four: Test the solution
I tested this solution by giving Claude AI the screenshot of the map above, the link to the initial visualization, and the following prompt:
I tried to improve the following visualization. https://www.visualcapitalist.com/ranked-the-worlds-50-largest-cities-from-1975-to-2050/
The screenshot is the visualization I made. 
Can you provide me some feedback to help improve my visualization. What is working? What is not working? What would make it work better?

Here is the feedback it gave me:

### Claude feedback
This is a solid start! Here's honest feedback:

#### What's working
- The color encoding for percent change is a smart choice — it immediately draws the eye to high-growth cities (dark blue in Africa/South Asia)
- The tooltip is rich and informative with ranks across multiple years, which gives real context
- Bubble size by 2050 population is intuitive and readable
- The title is clear and descriptive

#### What's not working
- The numbers on the bubbles (rank labels) are cluttering the map badly — overlapping each other and the bubbles, making it hard to read either
- The color legend is truncated — "SUM(Percent Change i..." is not a user-friendly label
- The size legend shows raw numbers like 8,661,000 instead of "8.7M" or "8.7 million" — hard to scan quickly
- The diverging color scale with -27% to 7164% is extremely skewed, meaning most cities probably look similar in color while a few outliers dominate the scale. A log transform or capping the scale would help differentiation
- No city labels on hover context — the rank numbers without names aren't useful at a glance

#### What would make it better
- Remove or hide the rank number labels from the map, or only show them on hover
- Rename the legend fields to plain English
- Format the size legend in millions
- Consider a log scale for the percent change color to handle the extreme outliers like Dar es Salaam
- Adding a small regional filter or highlight action could make it more interactive and explorable

### Synthesis
The feedback was very pragmatic and helpful. It caught some formatting things I had not noticed (legend titles) and the note about the scale coloring was very helpful. 

## Step five: build the solution
I implemented many of the suggestions. I ended up switching from percent change in population to change in rank. That required pulling in some extra data manually from the original visualization. I uploaded a new screenshot of the map to Claude and asked for more feedback and it suggested limiting the color scale to be 50 (the top value was originally 2000+ and was skewing the colors for all the other values) on the top end which I think makes sense as it is basically saying that those with 50+ values were not on the original list. How far off the list they were is interesting but it obscures the patterns of what happened to cities originally on the list which I think is important. 

## References
Our World in Data & Our World in Data team. (2018, January 25). *Definitions of world regions.* Our World in Data. (https://ourworldindata.org/world-region-map-definitions)[https://ourworldindata.org/world-region-map-definitions]

## AI acknowledgements
I used Claude AI to provide suggestions for my visualization as mentioned above and to troubleshoot Tableau. See the conversation in this (link)[https://claude.ai/share/eceda0a4-5a2c-48da-9c5c-4f33fb5e4a97].
