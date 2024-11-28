# Warrior-Cats
An analysis on coat color, gender distribution, population, and name usage in Erin Hunter's Warrior Cat series <br>
To view the finished dashboard, [click here](https://1drv.ms/x/c/4816316897784cf5/EfVMeJdoMRYggEh2AAAAAAABBOolGTjH8e7Uv3ANyn6tMw?e=cffiSN) <br>

### Update History ###
| Date | Version |Changes|
| ------------- | ------------- | ------------- |
|11/28/2024| 1.1|Added ASC 6, Fixed some names like 'Mediator Tree' -> 'Tree' and formulas that were calculating clan pop w/o Thunderclan |


### Programs Used ###
Excel

### Scope of Work ###
**Deliverables** <br>
- A clean dataset of all 7 current arcs
    - The Prophecies Begin
    - The New Prophecy
    - Power of Three
    - Omen of the Stars
    - A Vision of Shadows
    - The Broken Code
    - A Starless Clan
 - An interactive dashboard that details population per clan, the gender ratio, and the color of cats within each clan. The dashboard also includes top occuring character, top prefix, and top suffix.
 - An on-going project designed to be updated with each book or arc depending.

### Goal ###
The goal of this project is to analyze Warrior Cats', an active 20 year old fantasy young adult novel series, large cast of characters and identify any trends or unique changes that have occured throughout this cast over time. With a large fanbase, this dashboard can be used for the following potential use cases:
- Gender inclusion based on arcs or coinciding author change
- Gender Distribution
- Genetic Analysis of Cat coat color and its accuracy to real world cat genes
- Most reoccuring character overall or by coat color/clan
- Coat color analysis by Clan
- Book Arc Analysis

### Data Source ####
The orginal data is a dataset I have created myself. Below are details of its creation. You can access this raw dataset in xlsx format in the XLSX file above. I plan on updating it once or twice a year with book releases. Note, I do not claim to own any Warrior Cats Content. <br>
<br>
**Extracting the data** <br>
Character colors, gender, and clan were sourced from the Allegiances within each book. To get this data, I extracted the allegiance page from each book pdf and imported them into Excel with Power Query. This created source data that roughly looked like this: <br>
![image](https://github.com/user-attachments/assets/6ec04dae-9528-49aa-9974-3dbd38a89105) <br>
Although often, the data would be split amongst a few cells or be cut off onto the row below. More on that in the raw data transformations section. <br>

**Attribute Selections** <br>
The orginal scope of this dataset was to have the book, color, gender, clan, and name of each cat extracted from the source data. To keep the color attribute concise, only a few colors were used initally. Colors like the bicolors, tuxedo, cream, yellow, and calico, were added later as I could not find an accurate way to slot each cat into either gray or white when they were both. Brightheart in particular was painful to keep labeling white. Suffix and Prefix were also attributes added later and inspiration hit during the dashboard creation phase. Below is the possible options for each attribute:
| Attribute | Options |
| ------------- | ------------- |
|Name| Name of Cat|
|Gender| Male or Female|
|Clan| Thunder, River, Shadow, Sky, Wind|
|Color| Brown, Gray, Tabby, White, Ginger, Tortoiseshell, Bicolor grey & white (BicolorGW), Black, black and white (tuxedo), Bicolor brown and white (BicolorBrW), Cream, Yellow, Bicolor Brown and Cream (BicolorBC), Tan, Calico |
|Book| Common Book Acronym|
|Prefix| Name's prefix|
|Suffix| Name's suffix|

### Raw Dataset Transformations ###
In order to separate the data into color, gender, clan, and name attributes we had to tackle some big issues. Below is the transformations I made during this process. <br>
| Data issue | Issue Description | Solution |
| ------------- | ------------- |------------- |
| Inconsistent labeling across clan apprentices | Thunder clan apprentices listed twice, once under their mentor with no descriptors, and once in their own “apprentices” section with descriptors. Wind/River clan lists apprentices under mentors and add descriptors. Shadow clan lists apprentices with 0 descriptors Wind/River/Shadow do not have their own apprentice tabs|Remove Thunder clan duplicate apprentices w/o descriptors. Cross reference apprentices with [Warriors Wiki](https://warriors.fandom.com/wiki/Warriors_Wiki) to get descriptors. |
| Descriptor text cut off | Some descriptions were cut off and placed in their own row or column | Relevant descriptors were added back to orginal row and new rows/columns were deleted|
| "Apprentice, " | Some names have the word "Apprentice" in front. | Find and Replace tool used to remove |
| Different extraction formats | Not every PDF extracted in the same format | Manually corrected cut off data |
| Missing descriptors | Some cats didn't have any descriptors at all | Cross-Referenced Warriors Wiki and in cases where they could not be determined, excluded them from the dataset | <br>

### Attribute Creation Methods ###
- **Clan:** Cats were generally listed in order of clan in allegiances, these were just manually filled in as the data was cleaned.
- **Gender:** Cats were described as toms, she-cats, or queens. Using this data I initally used filter text contains... but later switched to a formula
- **Name:** Name was done using Excel's intelligent flash fill feature. Writing a couple of names auto-populated the rest.
- **Color:** Orginally used text contains, switched to a formula later
- **Book:** Added after each book was cleaned
- **Prefix and Suffix:** Used [Warriors Wiki Name Page](https://warriors.fandom.com/wiki/Names) to generate a list and then gave both prefix and suffix arrays defined names for easier formula use. Then created a formula to check the name for prefix and return it if it found it. This unfortunately resulted in names like Leaf leaf (due to leaf being in the prefix and suffix lists) and needed to be manually corrected after.

### Data Opportunities ###
There are opportunities to use this dataset in conjunction with real feral cat genetics. This dataset could also be used alongside sales numbers of Warrior Cat books to guage consumer interest over time. There is also an opportunity to gather protagonist demographics and analyze those over the same metrics the overall dataset is analyzed at. This dataset could also be used to add a personality, religious views, eye color or xenophobic attributes!<br>

### Finished Product ###
To view the finished dashboard [click here](https://1drv.ms/x/c/4816316897784cf5/EfVMeJdoMRYggEh2AAAAAAABBOolGTjH8e7Uv3ANyn6tMw?e=cffiSN)

### Data Limitations ###
With over, 4000 entiries and multiple authors there are bound to be mistakes in the books as well as in the dataset. The Warrior Cat Allegiances in particular are known to have several mistakes. The Warrior Cats Wiki does a great job of pointing this out [here](https://warriors.fandom.com/wiki/Mistakes_in_the_Warriors_Series). In some instances, I was able to catch these errors, such as a cat being given the wrong coat color, but I cannot promise I caught all of them. In addition, kits were left out of the dataset all together. They often weren't given descriptors and going forward in a book and finding them would've been troublesome. The cats also arent listed uniquely. Since the dataset relies so heavily on allegiance data, popular reoccuring characters like Firepaw, Fireheart, and Firestar, although they are all the same cat, are all treated as separate cats/entries. In addition Firestar in TPB 6 and Firstar in TNP 1 are treated as separate entries. The lack of unique identifier per actual cat isn't incredibly damaging to the dashboard but it does create some sway in the interpretation of color appearances. In some instances, certain sets of filters can cause Most Character Appearances to fill up with more than just 1 or 2 characters. This is due to ties in their amount of appearances. I've decided this isn't that big of an issue and creating a text box big enough to fit all of those names wouldn't be that productive. This same issue can be seen in the Prefix and rarely the Suffix category as well. If there is only one gender of a filtered cat color, this also breaks the Most populated clan category. 

### Reflection ###
Being my longest project, I'm incredibly proud of this dashboard and dataset. This task was incredibly ambitious for me but I learned a lot of valuable information about working with qualitiative data and creating dashboards along the way. I'm happy to have created something substational for a very formative series for me. With over 40 books, the Warrior Cats series offers a boon of potential data and a lot of fans in the space have created incredibly interesting insights. Being able to add to that space and expand on my data analytics skills was a great motivator for me. I plan on attempting to recreate the dashboard in more visualization platforms like Tableau. 

### Frequently Asked Questions ###
**Why isn't "paw" or "star" in the suffix category?** <br>
I found adding those would have skewed the point of the category. Of course there are a lot of apprentices and leaders, but lets look beyond that. <br>
**Why is ____ cat's coat classified as ___?** <br>
Certain decisions were made early on and through the creation of the dataset to keep classification simple. This may have resulted in some potentially dubious classifications. <br>
Some notable examples being:
- Cats with few color combinations such as Spiderleg 
  - ![image](https://github.com/user-attachments/assets/5a0adc75-99cd-4771-b881-6269c090d096)
  - Described as a black cat with brown belly, this cat is just labeled as black
- Any cat without a clear color to them such as Leopardstar and Silverstream
  - ![image](https://github.com/user-attachments/assets/37ca35b9-932c-4109-a8fb-5363d552151f)
  -![image](https://github.com/user-attachments/assets/b24f9a88-b6af-4489-8d0e-5768fa954748)
  - These cats are both labeled Tabby. This was done for ease of classification when using descriptors. Any cat that did not have an explicit descriptor like "Gray" or "brown" was listed as a tabby
- **How on earth do I use this dashboard?**
  - I find the dashboard opens easiest on Edge.
  - In terms of use, there are 3 "slicers" or filters. Book Arc, Color, and Clan. They all allow you to select individual things. Like you could select "Cream" under colors, "Omen of the Stars" as book arc, and "Shadow", you will be able to see the population of that criteria over the book arc, the gender distribution, and most commmon prefix and suffix associated with that criteria.
    - To clear the filter press this button located at the top right of the filters:
      ![image](https://github.com/user-attachments/assets/86de3e1b-95d2-4407-ad80-57ef6603f6e6)
    - To select multiple criteria within a filter, press the button next to the clear filter:
        ![image](https://github.com/user-attachments/assets/633e0157-815d-4dd0-a1bf-0380bf3e3495)
    - If one of the buttons is faded out, that is because there is no data for that category (for example, Sky clan does not exist until AVOS).
- **Can I use this data/dashboard to create my own analysis/visualization?**
  - I do not own Warrior Cats property, but as far as this dataset goes, you're welcome to use it/add on to it to create your own visualization. If possible, I would appreciate being credited or linking back to this page!



