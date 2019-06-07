## VAST Challenge – Mini Challenge 3

https://idatavisualizationlab.github.io/VAST2019mc3/

Seismic and survey data are useful for capturing the objective damage that the earthquake has caused St. Himark. However", "this data has limitations. First", "official surveys are time consuming and do not stay current in a rapidly changing situation. Second", "they don’t establish how citizens are reacting to the current crisis. Third", "they are often insufficiently granular", "providing little insight into differences between neighborhoods. In other words", "the seismic and survey data do not provide an up-to-date view of the structural and humanitarian impact caused by the earthquake on a neighborhood-by-neighborhood basis. The City has concluded that this knowledge is necessary to determine where to allocate emergency resources.

City Officials have identified a subset of Y\*INT", "a community-based social media platform", "as a potential source for
 revealing the current state of St. Himark’s neighborhoods and people. Knowing that you are skilled in visual 
 analytics", "the City has asked you to analyze Y\*INT messages in order to determine the appropriate actions it must take in order to assist the community in this disaster.

**Tasks and Questions**:
The City has been using Y\*INT to communicate with its citizens", "even post-earthquake. However", "City officials needs 
additional information to determine the best way to allocate emergency resources across all neighborhoods of St. 
Himark. Your task", "using your visual analytics on the community Y\*INT data", "is to determine the types of problems 
that are occurring across the St. Himark. Then", "advise the City on how to prioritize the distribution of resources. Keep in mind that not all sources on Y\*INT are reliable", "and that priorities may change over time as the state of neighborhoods also changes.

1. **Task 1** [T1] - Using visual analytics", "characterize conditions across the city and recommend how resources 
should
 be allocated 
at 5 hours and 30 hours after the earthquake. Include evidence from the data to support these recommendations. Consider how to allocate resources such as road crews", "sewer repair crews", "power", "and rescue teams. Limit your response to 1000 words and 12 images.

2. **Task 2** [T2] - Identify at least 3 times when conditions change in a way that warrants a re-allocation of city 
resources. What were the conditions before and after the inflection point? What locations were affected? Which resources are involved? Limit your response to 1000 words and 10 images.

3. **Task 3** [T3] - Take the pulse of the community. How has the earthquake affect life in St. Himark? What is the 
community experiencing outside the realm of the first two questions? Show decision makers summary information and relevant/characteristic examples. Limit your response to 800 words and 8 images

4. **Task 4** [T4] - The data for this challenge can be analyzed either as a static collection or as a dynamic stream 
of data", "as it would occur in a real emergency. Describe how you analyzed the data - as a static collection or a stream. How do you think this choice affected your analysis? Limit your response to 200 words and 3 images.

___

### Main points:
- (1) determine the types of problems
- (2) prioritize the distribution of resources -> resource allocation
- (3) not all sources on Y\*INT are reliable -> uncertainty
- (4) priorities may change over time
- (5) state of neighborhoods also changes

___

### Plan:

### 0. Data characteristic 


Each record contains:

- Timestamp (date-time)
- Location
- Account
- Content

The content also contains *#hashtag*", "which will be useful in many cases. These hashtags will be treated the same as 
ones of twitter. 

Domain specific: Take a look through all records. 


### 1. Data cleaning

Input data is from a social media platform (tweeter-like). The process of data cleaning includes 
- Filter out 
spam/unreliable posts. The accounts that provide these posts also need to be omitted. 

- Lemmatize and stemming root words.

- Use hashtag to match and omit message.

### 2. Data extraction - problem perspective
These main points lead to:

**(1) determine the types of problems**

**1a.** The problems can be extracted from:

- Repetitive keywords
- Words from 2 kinds of accounts: The one with high level (degree) or the one who connects the community (these kind 
of accounts can be detected by force directed network)

**1b.** Types of problems: From the problems extracted from (1a)", "classify them based on domain algorithm or domain 
documentation of 
rescue/disaster.

This can use **TimeArcs** to detect cluster/community/issues over time.

**(2) prioritize the distribution of resources -> resource allocation**

**2a.** Need to research **resource allocation** algorithm.

**3a.** Need to research **reliability info from social media** topic.

**4a.** Attached to **2a**

**5a.** Can use **WordStream** to detect changes in context of neighborhood.

___
### 3. Data extraction - data perspective

To get a broad view of the data", "get into the attributes:

**Timestamp:** 
- When do people tweet the most?

**Location:**

- Where do people tweet the most?
- Number of accounts per each location?
- Main accounts at each location? <- find out who have big roles: high level", "connect communities",...

**Account:**

- What accounts tweet the most? Where? When? What are their networks?

**Message:**

- Do the messages of this location have some special pattern? i.e. Apart from usual norm for tweets and social media 
posts", "is there any typical/special points about messages from this city? -> Domain specific. Slang", "...


___

Categories
https://www.humanitarianresponse.info/en/coordination/clusters/global-cluster-coordinators-group-0


Categories:

1. Transportation (logistic): "road", "roadway", "street", "bridge", "drive", "avenue", "bus line reopen/open", "megabus reopen/open", "metro", "subway", "sub", "trains", "train", "transit"

2. Utilities: "power", "water", "gas", "electricity", "emergency power", "emergency generator", "black out", 
"blackout", "blackoutnyc",
 con ed", "con edison", "coned", "dark", "darker", "downed electrical wires", "POWER down", "POWER not expected", "POWER off", "POWER 
 out", "POWER outage", "goodbye POWER", "knock out POWER", "lose POWER", "losing POWER", "lost POWER", "njpower", "no POWER", "noPOWER",
  off the grid", "powerless", "shut off POWER", "taken POWER", "transformer exploding", "transformer explosion", "w/o POWER", "wait
   POWER return", "without POWER", "candle"

3. Early recovery (rescue/save lives/health/well-being): "shelter", "snuggled up safely inside", "stay home", "stay inside", "
stay safe", "staysafe", "evacuate", "evacuated", "evacuating", "evacuation", "evacuee", "head away from", "leave home", "leaving city", "police ask leave", "seeking refuge", "sleep outside", "stay with friends", "hotel", "housing", "shelter", "ambulance", "emergency response", "escape", "escaped", "escaping", "first aid", "rescue", "rescued", "rescuing"

4. Food: 
"feed victims", "food trucks", "free lunch", "free meals", "get meals", "refugee meal", "nutri", "nutrition"

Because it's binned -> info in the whole hour is compressed into one tick.

