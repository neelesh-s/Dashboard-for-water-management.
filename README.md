# Dashboard-for-water-management.
Through this dashboard, you can analyze the trends in the water consumption of a certain area.

Abstract
This project aims to develop a web-based tool to process, visualize and analyze the flow rate and pressure in a water distribution system. The overall project is directed towards three main goals: 1) preprocessing the raw data to make it consistent and noise free; 2) development of a online web-based tool system to enable remote visualisation of the sensor data and water consumption trends; 3) analysing the data and inferring trends and patterns out of it. Data set from a water distribution system at IIT Jodhpur is used to demonstrate the capabilities of the developed tool and to demonstrate howincorporating web-based tool visualisations will be advantageous in decision making to meet the water requirement beforehand, optimize our operational inefficiencies, and spot potential leaks and pipe bursts. Finally, we discuss the future plans for the project.


Introduction
Water distribution system is a hydraulic infrastructure consisting of elements such as pipes, tanks reservoirs pumps and valves etc. It is crucial to provide drinking or potable water to the end users; hence, effective water supply is of paramount importance. In cities around the globe, the drinking water distribution infrastructure is aging rapidly and encountering failures with increasing frequency. The result has been significant water losses (imbalances between water entering and leaving the system), inefficiencies in system operation, and concerns about the quality of drinking water that is provided to the consumer
Monitoring of flows and pressures in a complex network has been of great challenge and interest for those involved with designs, construction and maintenance of public water distribution systems. Analysis and design of pipe networks create a relatively complex problem, particularly if the network consists of range of pipes that occurs in water distribution systems of large metropolitan areas. In the absence of significant fluid acceleration, the behaviour of a network can be determined by a sequence of steady state conditions, which form a small but vital component for assessing the adequacy of a network 
The scope of work in this domain is vast as there is limited on-line monitoring and analyzing capabilities within water distribution systems (usually at inlets to the water system), but also an increasing need to reduce wastage and other operational inefficiencies (such as power consumption), while all the time maintaining a supply system. The idea of a Smart Water Grid is becoming increasingly favoured as the natural next step to improve operational efficiency and improve understanding and prediction of demand and consumption in water systems


1.1  Challenges
From a water utility’s perspective, a Water Distribution System presents significant challenges in operational organization, for ex. handling the inefficiencies, preventing wastage of water, forecasting and preparing in advance for meeting demand and monitoring from remote location.
The data retrieval should be done frequently, meaning better analytics must be available to handle the flood of raw data into useful information, and this information must be acted on in an appropriate and timely manner.
Further challenges also include the problems of integration of sensors and other remote sensing systems with analytics and modelling softwares. 
The other major challenge which we encountered while working with data is the quality of data. The data received is noisy and inconsistent. The absence of a data storage device at the nodes does not allow us to log data in case it is not being sent to server. This leads to inconsistency in data.
**
1.2  Requirement of a web-based tool:

Decision-making aid: web-based tools can be used to track water consumption, monitor and spot trends, provide valuable insights into water consumption behavior and changes, and make better decisions.
Identify leakage and running water: By accumulating key data points and metrics, we can identify any possibility of the wastage of water.
Easy to share: web-based tools make it easy to share information with others, whether it’s through email, social media, or embedding the web-based tool on a website. web-based tool screenshots can be easily used in PowerPoint presentations.
Create flexible views of data by adding, removing, or repositioning elements. Support multi-page, tabbed layouts for different data sets.
Modify data views using filters and slicers.
In recent years, organizations have realized that accurate, and real-time monitoring of water consumption activities is crucial for the effective management of water grids and to induce conservation behavior both at the treatment plant and at the tap. For example, knowing that a bill equates to approximately 100m3 per month is interesting, but it does not inform the consumer if they are being efficient or wasteful, nor if this consumption is sustainable. As a result, it has been found that individual and organizational perceptions of water usage are often not matched with actual consumption.

1.3  Objectives: 
Development of a web-based tool to 
Pre-process the raw data obtained from sensors.,
Visualize and analyze the time series data of flow rate and pressure.
Infer and analyse the possible anomalies in the measured data obtained from the sensors.

2.  Work done
2.1 Methodology
 
2.1.1 Developing a web-based tool:

A web application has been made for the purpose of monitoring the flow rate, pressure, voltage, and water consumption. This has been made by using HTML, CSS, and Javascript.
HTML is the standard markup language for creating Web pages. Web browsers receive HTML documents from a web server or from local storage and render the documents into multimedia web pages. HTML describes the structure of a web page semantically and originally included cues for the appearance of the document.
Cascading Style Sheets (CSS) is a style sheet language used for describing the presentation of a document written in a markup language such as HTML or XML (including XML dialects such as SVG, MathML, or XHTML). CSS is a cornerstone technology of the World Wide Web, alongside HTML and JavaScript.
CSS is designed to enable the separation of content and presentation, including layout, colors, and fonts. This separation can improve content accessibility; provide more flexibility and control in the specification of presentation characteristics.
JavaScript is a high-level, often just-in-time compiled language that conforms to the ECMAScript standard. It has dynamic typing, prototype-based object orientation, and first-class functions. It is a multi-paradigm, supporting event-driven, functional, and imperative programming styles.
Apart from that, two libraries are also used, Chart.js and PapaParse. Chart.js helps us to make various charts and PapaParse converts .csv files to Javascript. The website consists of plots and an image of the campus depicting various nodes where sensors are installed. Through all these nodes, we obtain the flow, pressure, velocity, and voltage of the battery that powers it. The data about water consumption is obtained by integrating flow rate plots over the time axis.
We have used Pyscript so that the codes that are written for analysis in Python can be incorporated in the html page itself. This allows us to analyze in real-time and detect anomalies, this could lead us to detect leakages as soon as there are as we would see abrupt trends in the graphs. 
Lets talk about the various libraries used in the web-based tool.
pandas : 
It is used to read csv files by using the syntax below where URL is the online link of the csv..
      ice_data = pd.read_csv(open_url(url))
The value of URL is the link to the csv file.
Foreg: 
url= ("https://raw.githubusercontent.com/neelesh-s/Dashboard-for-water-management./main/all.csv")


It is used to convert date time in raw format to Python readable format.
Matplotlib: 
It is used set the dimensions of a plot.
It is used set the title of a plot.
It is used to give the data points and the type of graph.
It can also help with the aesthetics.
It can be used for the max no. of x-ticks.
It can be used for the labels
It can be used for the legend of the plot.
Numpy: 
Numpy is used for the mathematical tools used for analysis, for example, gaussian, and other mathematical operations involved in the analysis. 
Pyodide:
Pyodide is used by py script to access links on the web.
DateTime:
It is used to convert date time in raw format to Python readable format along with pandas.
Let's look at some other libraries.


jsPDF:
It is used to get an HTML division in a PDF format.
Dimensions of the div in the page can be set.
Also, the page size can be set.
html2canvas:
It is used to get a jpg file of any div with the click of a button.


2.2 Implementation
In the section 2.2, we go through all the different features that have been implemented in the web application.







2.2.1 Zone initialisation


The input is a csv file, the user has to place the link of the csv file in the underlying code.
The user shall make sure that the flow rate values are under flow column, and the pressure values are under the pressure column.


2.2.2 Data initialisation
If there any null values in the csv file, it would get detected.
Also separate data is being created for the graphs corresponding to rolling-mean and gaussian detection  analysis graphs.


2.2.3 Interpolation of data
For rolling-mean graph, we have a window size of 10, meaning that a certain datapoint would have the value of the average of the ten datapoints. This window size can be changed according to the user. Any null values will get a value.
For gaussian graphs, we evaluate the data by using the gaussian formulae. It smoothens the data and predicts a value for any datapoint, if the actual value is significantly different from the predicted value, then we consider it as an anomaly.
2.2.4 Raw data plot
“Raw Data” is in this case not the original data set. It is a data set that might contain interpolated data, as described in the previous sections. To generate a raw data plot, the user needs to insert data as described in section 2.2.1 
Output: • Plot of the raw data set of flow rate and pressure
2.2.5 Flow-rate pressure plot
A plot that shows the raw data corresponding to the flow rate and pressure on the same graph to visualize trends. The input is taken from the CSV file provided by the user as described in 2.2.1
2.2.6 Rolling mean plot
Here, for each datapoint, the existing value is replaced by the ten adjacent values, the number 10 could be changed to anything that the user wants. The input data is the CSV file as described in 2.2.1
2.2.7 Gaussian smoothing plot
Here, the graph is smoothened by using the gaussian formulae, it uses the adjacent 100 values to do the smoothening. for each datapoint, the existing value is replaced by the new value, the number 100 could be changed to anything that the user wants in the underlying code. The input data is the CSV file as described in 2.2.1
2.2.8 Gaussian anomaly detection plot
Here, an anomaly is that datapoint where the predicted value and the real value differ by more than 20 percent. It could be due to anything like leakage, shutdown of supply, etc. The points where the anomaly is detected is shown by a green line. The user input and the gaussian smoothening is done by the method as described in 2.2.7


2.2.9 Gaussian anomaly detection plot
Here, an anomaly is that datapoint where the predicted value and the real value differ by more than 20 percent. It could be due to anything like leakage, shutdown of supply, etc. The points where the anomaly is detected is shown by a blob on the data point itself. The raw data plot is also plotted on the same graph.  The user input and the gaussian smoothening is done by the method as described in 2.2.7
2.2.10 Average flow rate
In this plot, the average flow rate for the entire day is plotted. This helps us to predict the consumption of the entire day. The user input is as described in 2.2.1.
2.2.11 Average pressure
In this plot, the average pressure for the entire day is plotted. The user input is as described in 2.2.1.
2.3 Challenges in making a web-based tool
It's difficult to integrate the codes for analysis which are written in Python to be integrated in the node environment, therefore, we are using Pyscript so that we could use HTML, CSS, and Javascript to get the desired dashboard, As py-script technology is very new as it was launched on May last year, it is not as efficient as ReactJS, but it solves the problem of analysis in the dashboard itself.
When any online resource was referred to make or understand something, a lot of time was wasted on an outdated source of information, which is not mentioned on the video. It was only realised when the code was written and the desired output was not obtained.
In making a web-based tool, we have to make sure that the different versions of different libraries that we use are compatible with each othe . It occurred quite a few times that the latest versions of py-script were not compatible with the latest versions of python libraries
As the py-script technology is effectively a few months old, we still dont know if certain features are provided by py-script or not. For, example, taking a text input and working on it in the python virtual environment. This led to a lot of trial and error, and a wastage of time. Some of the time the desired functionality was obtained, but not for most of the times.









3. Results and discussion
3.1 Flow rate pressure chart

In the above figure, we see the blue lines which represent the flow rate, and the red line represents the flow rate. The image above is generated by the click of the ‘download image’. We see regular trends of water supply shutdown through this image.

3.2 Flow Rate Plot

In the above figure, we see the blue lines which represent the flow rate. The image above is generated by the click of the ‘download image’ . We see regular trends of water supply shutdown through this image.
3.3 Rolling mean flow rate plot

In the above figure, we see the red lines which represent the flow rate. The image above is generated by the click of the ‘download image’ . We see regular trends of water supply shutdown through this image. We also see that the data has been smoothened to some extent.

3.4 Gaussian smoothening plot for flow rate

In the above figure, we see the black lines which represent the flow rate according to raw data, and the red line represents the flow rate according to Gaussian formulae. The image above is generated by the click of the ‘download image’. We see regular trends of water supply shutdown through this image. We see that the red ones are more smoothened than the black ones.

3.5 Anomaly detection plot

In the above figure, we see the blue lines which represent the flow rate. The image above is generated by the click of the ‘download image’ . We see regular trends of water supply shutdown through this image. Here, the anomalies are detected by the green line.
3.6 Anomaly detection plot

In the above figure, we see the black lines which represent the flow rate from raw data, and the red line represents the flow rate upon smoothening. The image above is generated by the click of the ‘download image’. We see regular trends of water supply shutdown through this image. The blob represents the anomaly. We can directly see the difference between the real data and the predicted value and predict the reason for the anomaly.

3.6 Plot for pressure

In the above figure, we see the blue lines which represent the pressure. The image above is generated by the click of the ‘download image’ . We see regular trends of water supply shutdown through this image.

3.7 rolling mean plot for pressure

In the above figure, we see the red lines which represent the pressure. The image above is generated by the click of the ‘download image’ . We see regular trends of water supply shutdown through this image. We also see that the data has been smoothened to some extent.
3.8 Gaussian smoothened plot for pressure

In the above figure, we see the black lines which represent the pressure according to raw data, and the red line represents the pressure according to Gaussian formulae. The image above is generated by the click of the ‘download image’. We see regular trends of water supply shutdown through this image. We see that the red ones are more smoothened than the black ones.



3.9 Anomaly detection for pressure

In the above figure, we see the blue lines which represent the pressure. The image above is generated by the click of the ‘download image’. We see regular trends of water supply shutdown through this image. Here, the anomalies are detected by the green line.

3.10 Anomaly detection in pressure through a blob

In the above figure, we see the black lines which represent the pressure from raw data, and the red line represents the pressure upon smoothening. The image above is generated by the click of the ‘download image’. We see regular trends of water supply shutdown through this image. The blob represents the anomaly. We can directly see the difference between the real data and the predicted value and predict the reason for the anomaly.
3.11 Average flow rate plot

Here, we have the average flow rate throughout the day, from this, we can get the total consumption of the day.

3.12 Average pressure plot

Here, have the average pressure throughout the day


4. Conclusion
Development of an online web-based tool portal has not only assisted in monitoring and analyzing capabilities within water distribution systems but also an increasing ease of reducing wastage of water and other operational inefficiencies
We conclude that we can make better decisions on how we consume water. Having data on an hourly basis can help us understand what we can do to use less water to get lesser water bills and save more water.
We also see that we use approximately four times the amount of water than during shutdown. This depicts that for that period, although we had a water supply from tankers, we definitely saved a lot of water. We also saw the water demand trends and how the demand peaks three times in a day. We are now able to understand weekly trends of water demand. Also, any water disruptions of leakages in a pipeline can be identified and acted upon immediately. 
Overall, having web-based tools like these at least makes organizations think about how they can use water judiciously which is a positive for the betterment of the future as water consumption is expected to increase by 40% in the coming years.








