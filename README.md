Materials Research

This article will be laid out as a process flow until I further understand my intended process. It will be more technical in nature than some of my other writings and surround implementation. 
The article “aflow.org: A web ecosystem of databases, software and tools” refers to a logical method. It states, “To enable materials databases supporting computational and experimental research, it is critical to develop platforms that both facilitate access to the data and provide the tools used to generate/analyze it — all while considering the diversity of users’ experience levels and usage needs.” (Esters et al. 1). 

Part 1: The source data
Perhaps the most applicable resource I have found through my extensive research of this topic is the materials project. An open-source app that can be found here: https://materialsproject.org/. According to the documentation it is intended to be used/shared openly and is licensed under the creative commons 4.0 license. This was a major reason for selecting this dataset. Many incredible minds have already started the conversation however, it is a new area of study for me. 

Part 2: The programming
The Materials Project API outlines python programming as a preferred method and a git repository https://github.com/materialsproject/api that provides access to raw data. 

Mongo db was a great option for storing data. In our example we queried our dataset from the API and saved it as a comma separate values file (excel). We cleaned it using Python and Excel. It was then stored in a locally hosted Mongo database. Ubuntu Docker image was my preferred method.

At this point, data should be fed through an algorithm (TBD) to output the desired unknown variables. My next steps are delving further into the sciences to develop a greater understanding as my current knowledge on the subject is lacking. I found the write_to_csv functionality in python to be particularly useful to this point.

Due to the technical nature of this topic, I was careful to thoroughly comment the code for people new to the subject. This was particularly important to me as I had zero understanding of Python 1 month ago.

The code that accompanies this paper does not reveal any answers to scientific mysteries. It does show some of the functionalities available with a working example someone could adapt to their own purposes. It is intended to gather my thoughts into one place and be approachable for a novice user.

The model uses linear regression, random forest regression, feature importance as well as a k 1-25 iteration. I highly encourage interested people to watch a video on these topics individually as I found them to be particularly interesting topics. I hope to be able to apply all of these regression concepts to more thoughtfully selected material properties in the future. 

We presented this project to a live group and believe it was pretty easy to follow the examples. We did have a question surrounding the K 1-25 iteration that after digesting, I feel better prepared to answer. 

• The question was on a K 1-25 iteration; how do you know which is best? 

The question is complex because it can be answered 2 ways, I will try and clarify for transparency. 

The simplest explanation is that the code iterates or runs loops using a different value for K each time. We plot the accuracy of each run separately along the x axis. K 1-25 is on the x axis and accuracy is measured on the y axis. The simple answer would be, wherever the line is the highest we would say it is most accurate. The image in the PowerPoint would show an example of this.

There is likely a follow up question I was considering during the presentation. The follow up question requires some additional thought. It would be:

• What datasets would be best for different K Values? 

In thinking about this further, my thoughts are as follows. We use the concept of train_test_split 80/20 so we have the ability to “check the work” of the regression model. For example, let’s say we run K1. Then we use some of the data (20% that was set aside at the beginning) to see to what extent the model was accurate. Then we run the K2 and so on and so forth.

If we use the plotted point itself (IE K1 model), it likely best reflects it’s own values. The 25th closest point value likely does not as closely represent the values of the plotted point. This might not be true in all datasets or there could be a different logic. I would think in most cases a lower K-value would be more accurate but it depends on application, I suppose. I would pay close attention to the K 1-3 unless the data seems to indicate something different. I hope this helps someone.

Thoughts on User interface:

If I were continuing this project, user interface would be a web-app using Flask and the following technologies:

https://flask.palletsprojects.com/en/2.3.x/
https://www.mongodb.com/
https://mathjs.org/
https://www.chartjs.org/

I felt each of these were applicable. More information can be found in their documentation. I liked the idea of “drag and drop” and “add your own formula” functionalities with simplicity in mind. A UI with buttons would be a nice alternative to the command line when implementing the regression/machine learning aspects.

Part 3: The algorithm
It is currently unclear what the most desirable output would be or whether my current thoughts on the matter will be in any way relevant by the end of undergrad. Due to the amount of interest in the subject and the nature of the website/features, there are countless brilliant people testing different possibilities and algorithms already. 

As for me, I will continue my studies in the sciences. Keep in mind, at the time of this article, I am a sophomore in undergraduate studies. As for this playground, I will continue to use the data to perform calculations, apply formulas and store data in various outputs until I am more solidified in my objectives. 

Part 4: The results.
This process will serve as a first step in establishing a repeatable process for myself (and anyone who wants to use it) for continued learning. Using the known data [materialsproject.org] as inputs, processing locally [Python], storing locally [Mongo], applying mathematical formulas and outputting in a spreadsheet [Excel] format.

Final Thoughts
I am focused on Mathematical and Chemistry related formulas which will occupy my thoughts in the upcoming semester. At the Department of Energy, I learned concepts that course corrected my understanding and will continue to pivot as I learn more.

A few questions:

• What would be most valuable to employers in material-related fields? 

• Is there desirable knowledge or valuable skill-sets in new hires? 

• Are there specific metal characteristics, calculations, laws, theories, etc. that could be used to further refine and declare the algorithm?
	
This project acts as a great starting place to collect ideas and further my knowledge. While the pursuit of knowledge is far from complete for those of us in undergraduate studies, this is a great first step. With over 19,000 citations to this amazing wealth of information [materialsproject.org], I have likely just seen a glimpse of what is possible. This project could not be completed without a special thank you to everyone that makes materialsproject.org possible. The Department of Energy provided incredible resources surrounding regression modeling, Python, and statistical analysis.



Citations

M. Esters, C. Oses, S. Divilov, H. Eckert, R. Friedrich, D. Hicks, M. Mehl, F. Rose, A. Smolyanyuk, A. Calzolari, X. Campilongo, C. Toher, S. Curtarolo, aflow.org: A web ecosystem of databases, software and tools, Computational Materials Science, Volume 216, 2023, 111808, ISSN 0927-0256, https://doi.org/10.1016/j.commatsci.2022.111808.
A. Jain, S. Ping Ong, G. Hautier, W. Chen, W. D. Richards, S. Dacek, S. Cholia, D. Gunter, D. Skinner, G. Ceder, and K. Persson, "Commentary: The Materials Project: A materials genome approach to accelerating materials innovation", APL Materials 1, 011002 (2013) https://doi.org/10.1063/1.4812323# DOEMaterials
