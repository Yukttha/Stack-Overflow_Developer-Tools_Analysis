# Stack OverFlow Developer Tools Analysis
Project Focus: Network Analysis
<p>Dataset Source: http://www.kaggle.com/datasets/stackoverflow/stack-overflow-tag-network

<!DOCTYPE html>
<html lang="en">
  
  <head>
    
  </head>
  
  <body>

  <h3>Libraries</h3>
  <li>NumPy</li>
  <li>Pandas</li>
  <li>Matplotlib</li>
  <li>Networkx</li>

  <h3>I. Overview of Dataset</h3>
  <p>The dataset focuses on technology tags based on Developer Stories from Stack Overflow. Stack Overflow is a Q&A platform that allows developers to ask questions, learn, and share technical knowledge. Developer Story allows users to share what they have worked on by linking features they worked on, blog posts, or public code. Essentially, it allows for users to share their most proud work. 

The dataset is stored in a csv file, with three variables, represented as columns: Source, Target, and Value. Source is the technology tag, Target is the other technology tag, and Value is weight representing the frequency of co-occurrence of the two tags, indicating how often these tags are used together in application development.</p>
  
  <h5>Objectives</h5>
  <li>To identify which tags, hold strong and weak significance in the network.
  <li>To identify the relationship between nodes and edges and apply to real-world applications.
  <li>To identify why isolated communities exist and apply to real-world applications.

  
  <h3>II. Social Network Analysis and Visualization</h3>
  <p>The technology tags represent various programming languages, frameworks, and tools. Using GenerativeAI (ChatGPT), we categorized the nodes and edges to identify for any commonalities that we may use the analysis. Some of these tags may overlap with more than one category.

  <h5>Basic Metrics of Networks</h5>
  <li>Undirected graph: Number of nodes that exist is 115 and the number of edges is 245. 
  <li>Directed graph: Number of nodes that exist is 115 and the number of edges is 490.
  <li>There are six components each component representing a subgraph. 
  <li>Subgraph 0 had the most nodes with 102, with the least density of 5%. 
  <li>Minimum node cut is json, which means removing json would disconnect the graph. The minimum edge cut is AngularJS, and Angular2, which if these two edges are removed between two nodes, it would disconnect the graph.

  <h5>Network Characteristics</h5>
  <p>Based on the spring layout of the network, we can see that there are five isolated clusters that are not connected to the main cluster. The main cluster is strongly connected, has high internal density, sparse external connections with five isolated clusters.  </p>

The 5 isolated clusters are identified below:
  <li>Cluster #1: perl, regex
  <li>Cluster #2: excel, vba, excel vba
  <li>Cluster #3: agile, tdd
  <li>Cluster #4: hadoop, apache-spark, scala
  <li>Cluster #5: selenium, testing

  <h5>Centrality</h5>
  <p>To identify which node holds the most centrality of a network three centrality measures can be used to identify the most central node: Degree Centrality, Betweenness Centrality, Closeness Centrality. 
  <li>jquery was the highest value in all three measures of centrality, meaning it is more connected to the other technology tags. 
  <li>The lowest values in all three measures included multiple tags, therefore, we had to look for the common tags: tdd, regex, testing, selenium, perl, and agile. This means that these technology tags with the lowest values found in all three measures of centrality are more isolated, and not used commonly. 

  <p>To analyze further of the node that holds the most centrality, we did a social network extraction by extracting ego network based on the ego node jquery.</p>  

  <h3>III. Insights and Patterns to Managerial Implications</h3>
  <p>A common pattern was jquery found to have the highest value in all three measures of centrality: degree, betweenness, and closeness. This leads to the next question, of <b>why that may be the case? </b>
<br>
  <p>Based on external research, it is found that jQuery is a JavaScript library, which is considered to be fast and small, with its combination of versality and extensibility it has impacted many users the way they code in JavaScript (jQuery, 2024). jQeury makes processes easier in taking many of the common tasks that require many lines of JavaScript code with a single line of code. Additionally, it is found that many of the biggest companies use jQuery, for example Google, Microsoft, IBM, and Netflix (W3Schools, 2024). In terms of managerial implications, companies may look to opt developers to use libraries that make processes more efficient and simplifies the number of lines of codes used.</p>

  <h5>Analysis of Isolated Clusters</h5>
<p>Upon further research of Developer Story, it has found to have been discontinued as of April 1, 2022. Therefore, the analysis may not fully correspond to the current market demands of technological tools, programming languages, and frameworks. Interestingly, we see that VBA, Excel, and Excel-VBA are not part of the connected network, and this is logical as we know that Developer Stories allow users to share their work, specifically on coding. Thus, developers are less likely to use these tools and have a lower tendency to share their work using tools commonly used in business context (e.g., finance, accounting, etc.).</p>

<h6>Perl</h6>
<p>Perl is not connected to the network as it may be for many reasons, including that the language was created in 1987 and it is Unix-friendly. It is a high-level, interpreted language, commonly used for system administration. Perl usage has declined due to Python dominating the system administration space, and the language’s complex syntax making it difficult to capture more users.</p>

<h6>Scala</h6>
<p>Scala has a steep learning curve and with the dominance of other languages like Java and Python has limited its growth.</p> 

<h6>Hadoop</h6>
<p>Hadoop is also part of the isolated clusters, and this may be due to the cloud technology growth, which most companies provided big proprietary, and there are other reasons, such as scaling creates a challenge.</p>

<h6>Regex</h6>
<p>Regex (aka. Regular expressions) can be more difficult to read and write and can get complicated. It can be inefficient, due to its complexity. This can be connected to why Regex is part of the isolated communities.</p>

<h6>Selenium</h6>
<p>Selenium is part of the isolated communities, and this may be in relation to the decline in usage. Selenium is used for automation testing, but other tools have taken over, such as Cypress (automation-as-code tool using JavaScript).</p>

<h6>Agile</h6>
<p>Agile refers to software development methodologies for a set of frameworks and practices based on the principles in the Manifesto for Agile Software Development. Due to this, we assumed that developers may be less likely to share or contribute their work on methodologies, and more likely to share their work on programming.</p>

<h6>Apache-Spark</h6>
<p>Apache-Spark is part of the isolated clusters as it may be because it is commonly used in data engineering, which makes it niche, in terms of its relevance. There is another framework, which is Apache Flink and it is considered to be more faster than Spark. It is important to note that this information was retrieved in 2024, after the Developer Story was terminated in 2022.</p>

  <h5>Insights</h3>
<p>The technology tool itself is not commonly used in the developer world, other languages and frameworks have become more popular due to versality, and short learning curve, effectively attracting more users to use that technological tool. Businesses should look and pay attention to the trends of what languages and tools are used commonly, so that their workforce is equipped with developers that keep up with current trends and can find resources available on platforms, like Stack Overflow.</p>

  <h3>IV. Summary and Conclusion</h3>
<p>In conclusion, we find that there were 5 isolated communities, and each node was identified as to why that technology tag was not part of the highly dense network. A common reason was for the languages, tools, or frameworks may have been too complex, declined over time, and other technologies overtake it, leading to less connectivity of the tags in Developer Stories. A suggestion that can be made for further research is looking at a dataset of what programming languages, tools, and frameworks are commonly used in various industries, and whether that plays a profound role in users using those tags in the Developer Story. Furthermore, it is found that languages, frameworks, or tools that are simple, such as the jQuery library are found to play a role in the centrality of the network. This shows the behavior of developers, who tend to opt for more simplicity utilize such tools. However, more research is required to understand this portion, such as focusing on libraries versus programming languages.</p>
 
  </body>
</html>
