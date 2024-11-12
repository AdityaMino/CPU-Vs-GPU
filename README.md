[![Python](https://img.shields.io/badge/Python_3.9-Green?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![JupyterLab](https://img.shields.io/badge/JupyterLab-E36209?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-blue?style=for-the-badge&logo=plotly&logoColor=white)](https://matplotlib.org/)

# CPU💻 Vs 🎮GPU - Exploratory Data Analysis of the Semicon Industry
## 💡Abstract 
This project presents an in-depth exploratory data analysis (EDA) of a dataset comprising 2,185 CPUs and 2,668 GPUs to examine the trends and advancements in semiconductor technology. The dataset present in this Analysis has information about releases of CPU and GPU from to the year 2000 to 2021, including, but not limited to, its release date, frequency, Vendor, commercial name, TDP, etc. 

 
By investigating key industry phenomena, such as Moore's Law, Dennard Scaling, and the trend of GPU performance doubling approximately every 1.5 years, this analysis provides valuable insights for researchers, designers, and industry stakeholders. Through data cleaning, processing, and visualization techniques using libraries like Seaborn, Matplotlib, and Plotly, this project offers a comprehensive understanding of historical trends and their 
implications for future developments in CPU and GPU performance. 

## 📑 Contents

- [💡Abstract](#abstract)
- [⚙️Introduction](#introduction)
- [🔎Literature Survey](#literature-survey)
- [🛠Methodology and Working Principle](#methodology-and-working-principle)
- [📊 Result Analysis](#result-analysis)
- [🧭Conclusion](#conclusion)
- [🌐 Future Scope](#future-scope)
- [📚 References](#references)

---

## ⚙Introduction
In consumer and business applications, the difference between Central Processing Units (CPUs) and Graphics Processing Units (GPUs) has grown in importance as technology develops. CPUs are made for general-purpose computing and have historically served as computers' primary computational core. GPUs, on the other hand, are designed for parallel processing and are now essential in fields that require a lot of processing power, such virtual reality (AI), gaming, and data-intensive applications like scientific simulations and machine learning. GPUs were first developed for graphical rendering, but in recent years, as AI and deep learning models have proliferated, they have become essential computational tools for processing massive datasets and carrying out matrix operations quickly. As a result of this change, there is now an increasing amount of research devoted to comprehending the applications, performance, and efficiency at which CPUs and GPUs individually shine. By looking at trends in processing power, transistor counts, die sizes, and other pertinent metrics,this study seeks to investigate and analyse the data pertaining to CPU and GPU

<img src="https://github.com/user-attachments/assets/cd9b5aa9-f2b2-4e0a-b5b6-9aa7b36d316d" alt="image" width="520" height="350">

**Fig- Pie Chart Depicting the number of CPU’s and GPU’s in the dataset**

This project aims to analyze a dataset of thousands of CPUs and GPUs, examining attributes such as process size, die size, transistor count, and release dates. By doing so, we can assess 
the validity of these long-standing industry trends and explore how closely modern developments align with them. This analysis is expected to yield insights valuable for hardware designers, researchers, and technology forecasters in anticipating future 
improvements in computational power and optimizing both hardware and software solutions. Python is a powerful and flexible programming language, well-suited for data analytics due to its readability, extensive libraries, and straightforward integration into data workflows. Its ecosystem supports the entire data analysis pipeline, from loading and processing data to performing complex analyses and visualizations.

<img src="https://github.com/user-attachments/assets/33ea3882-a60e-407c-a6be-bb7974e08d1c" alt="image" width="600" height="350">

**Fig - Moore's Law is powering technology**

## 🔎Literature Survey 
A sizable amount of literature that explores the evolution, performance measures, and applications of CPU and GPU architectures has been bolstered by continuous study and development. The historical significance of Moore's Law in influencing the development of CPUs and GPUs was emphasised by Hennessy and Patterson (2019). Moore's Law has mostly impacted CPU development, even though it predicted that transistor counts would double roughly every two years. However, parallel developments have also benefited GPUs, especially due to the growing demand for graphics rendering and, eventually, AI-driven applications (NVIDIA Research, 2020). Other research, like those by Jouppi et al. (2017), highlight how important GPUs are for speeding up machine learning tasks and demonstrate how much better GPUs are at parallel processing than CPUs. Because of this, they are more effective at activities requiring the simultaneous processing of several data points, such as training neural networks. Borkar and Chien (2011), on the other hand, talk about how CPUs still rule serial processing applications where single-thread speed and task switching are important.

## 🛠Methodology and Working Principle
With an emphasis on trends and performance measures, this project compares and analyses CPUs and GPUs using standard methodology. As shown below, the methodology consists of data loading, preprocessing, cleaning, exploratory data analysis (EDA), and visualisation. 

➢ **Data Loading** - Reputable public datasets and product specifications provided the data on different CPUs and GPUs, including characteristics like clock frequency, transistor count, process size, and year of introduction. Because the data is placed into a structured format, analysis and manipulation can be done quickly. Our Dataset is known as “CPU and GPU Performances Dataset”, which is publicly available on Kaggle.com website.  
Here are some interesting facts supported by the data, which we will verify based on our insights- 
 
- Moore's Law still holds, especially in GPUs. 
- Dannard Scaling is still valid in general. 
- CPUs have higher frequencies, but GPUs are catching up. 
- GPU performance doubles every 1.5 years. 
- GPU performance improvement is a joint effect of smaller transistors, larger die size, and higher frequency. 
- High-end GPUs tends to first use new semiconductor technologies. Low end GPUs may use old technologies for a few years

➢ **Data Preprocessing** - To guarantee consistency, the data is pre-processed after loading. After our initial look, we have seen a brief overview of our dataset and determined that we have around 4800+ rows of data and 14 columns as well as their respective data types. Right from the get-go, we can see "NaN" values under the FP16 GFLOPS, FP32 GFLOPS, and FP64 GFLOPS columns, hence we will drop those columns, and handle other missing data as well.

Records lacking important information, such as the release date, are eliminated, and missing values in numerical fields such as transistor count, process size and die size are replaced with mean values. Change numerical attributes to the proper data types (floats 
or integers) and date fields to datetime formats. Set release_date to datetime64, since it is being treated like an object, similarly set procss size to integer type.  

<img src="https://github.com/user-attachments/assets/13fc142a-2862-4c62-a7be-bfa36bef3615" alt="image" width="600" height="450">

**Fig-Flowchart depicting the program flow**

 ➢ **Data Cleaning**- By eliminating extraneous information and inconsistencies, data cleaning improves the dataset.
- Dropping Duplicates and Outliers: Ensures uniqueness and accuracy. 
- Filtering Irrelevant Data: This method focusses on the essential CPU and GPU features by eliminating data points that don't contribute to the research. 
- Converting into categories: We can group data into categories such as Type(GPU or CPU) , Vendors( AMD, Intel, Nvidia etc.) based on extracted patterns from model names or other attributes, to help us in visualisation. 

➢ **Exploratory Data Analysis (EDA)** – The EDA stage sheds light on important characteristics and patterns -
- Scatter Plots: Analyze the relationship between variables like Process Size vs. Frequency and Die Size vs Transistors.
- Bar Charts: Used to understand Foundry and Vendor distribution in the market. Also used to show counts or averages for frequencies, transistors and process size.
- Correlation Analysis: Use heatmaps to examine overall correlation and separate correlations within CPU and GPU parameters.
- 3D Visualization: Visualize multi-variable relationships (e.g., process size, die size, transistor count) with 3D scatter plots.
- Box Plots – These give accurate lower, upper and average values of the feature under consideration.

➢ **Visualization** - Use libraries like Seaborn, Matplotlib, and Plotly for advanced visualizations, such as:  
- Transistor Count vs. Release Year
- Process Size vs. Release Year
- Frequency vs Release Year
- Chip Manufacturer Market Share (Bar Plogt)
- 3D Scatter Plot for chip attributes
  
And many more, we draw conclusions from the visualizations and analyses, such as trends in transistor counts over the years, reduction in process size, and foundry contributions. Summarize statistical findings (e.g., correlation between process size and die size) and provide business insights related to vendors and technological advancements. 

![image](https://github.com/user-attachments/assets/1ff46d47-d3f5-43a9-91f9-f029c2c0fc42)

**Correlation Matrix of CPU and GPU**

## 📊Result Analysis
The analysis of the CPU and GPU dataset revealed significant insights into trends and advancements in semiconductor technology, particularly in relation to Moore's Law, Dennard Scaling, and the rapid improvements in GPU performance. Key metrics such as process size, die size, transistor count, and operating frequency were examined across thousands of CPUs and GPUs from various vendors, leading to several key findings:

- **Transistor Count Growth:** The analysis showed an ongoing increase in transistor count over time, consistent with Moore's Law. Both CPUs and GPUs demonstrated exponential growth in transistor counts, with GPUs advancing at a faster rate, which aligns with the observed trend of GPUs doubling in performance approximately every 1.5 years.

![image](https://github.com/user-attachments/assets/c717fb6a-0676-40b3-a751-68aabeb5ca2b)

**Increasing trend of Transistors as per Moore’s Law**

- **Reduction in Process Size:** The data highlighted a steady decrease in process size, underscoring advances in semiconductor manufacturing. CPUs and GPUs alike have seen continuous reductions in process size (measured in nanometers), reflecting industry efforts to enhance performance while keeping power consumption manageable, as proposed by Dennard Scaling.

![image](https://github.com/user-attachments/assets/f366716a-f434-4f9c-880d-60b74de94f57)

**Decreasing trend of Process Size**

- **Frequency and Performance Trends:** While gains in CPU frequency have slowed down in recent years, GPUs have continued to see improvements in performance and efficiency, especially for tasks requiring parallel processing. This trend highlights the industry’s shift toward multi-core CPU designs and the optimization of GPUs for high-throughput applications.

![image](https://github.com/user-attachments/assets/11fd0bc7-7474-452a-ac36-715bbbd172a4)

**Exponential Increase in CPU Frequencies**

•	Vendor-Specific Trends: By comparing data across different vendors, unique trends became apparent. Some vendors focused on reducing process size and power consumption, while others prioritized transistor count or frequency to boost performance. The dataset showcased each vendor’s unique approach to pushing semiconductor technology forward.

![image](https://github.com/user-attachments/assets/ee1258bb-5697-42f3-af93-19c5e47b26e9)

**TSMC has majority of market share**

A range of visualizations, including scatter plots, bar charts, and line graphs created with Seaborn, Matplotlib, and Plotly, visually represented these trends in CPU and GPU evolution. These charts illustrated relationships between release dates, transistor counts, process sizes, and performance metrics, providing a clear view of historical and emerging trends.
This analysis offers valuable insights for stakeholders in the semiconductor industry by highlighting historical trends and aiding in the prediction of future developments. These findings provide a foundation for hardware designers and software developers to anticipate advancements in computing power and optimize future technologies accordingly.

![image](https://github.com/user-attachments/assets/0a1ad6d6-54bc-4369-ad0f-27d585f6f08c)

**AMD & Intel are the Frontrunners of the market**

![image](https://github.com/user-attachments/assets/9aa4acc7-bd93-472b-83f7-9bf372dd177b)

**AMD and Intel have the highest frequencies**

## 🧭Conclusion 
The unique evolution and specialisation of each processor type in response to various computational demands is revealed by the exploratory data analysis on CPUs and GPUs. CPUs, which are typically designed for general-purpose computing, show a steady trend of striking a balance between moderate parallelism and single-threaded speed. The following conclusions are deduced from the multiple plots-

- The leading manufacturers of CPUs and GPUs include five prominent brands: **Intel, AMD, NVIDIA, and ATI.** However, further research revealed that ATI was 
acquired by AMD, making AMD and NVIDIA the primary manufacturers of GPUs today. 
- Meanwhile, Intel and AMD remain the main competitors in the CPU market, where we’ve noticed that these two brands offer a wider range of frequencies 
compared to those in the GPU market. We can clearly notice the rising trend of frequencies and that CPU Frequencies are significantly higher than GPU 
Frequencies. Overall, we observed that CPUs have traditionally been faster and performed better than GPUs. However, a steady trend shows that GPUs are 
gradually closing the performance gap each year.
- As suggested by our data, most of our parameters have a negative correlation with Process size, which generally means more advanced technology is integrated into 
our processors which then results in performance, since a smaller process size leads to more transistors efficiently packed onto a chip. GPU’s also pack a greater 
number of transistors, as the years progress.

![image](https://github.com/user-attachments/assets/57c93de0-7734-4a71-bc6c-6e1b87b98f63)

**Gradual Increase in Transistor vs Die Size**

- A larger die size, which physically holds the transistors, provides more surface area, allowing for an increased number of transistors, leading to enhanced 
frequency performance in both CPUs and GPUs. Our analysis indicates that advancements in these processors are influenced by a combination of larger die sizes, higher transistor counts, and increased frequencies. This trend is more prominent in GPUs than in CPUs over time. 
- In terms of Foundries, GF have very recently emerged in the market and In the past few years, it has scaled up its Frequency Values close to the level of Intel And TSMC. Although TSMC was present for many years, its frequency values have very recently increased.
- For Moore's Law to be upheld, there must be: Negative correlation between Process Size and Time Positive correlation between Transistors and Time. This is verified by our data, hence Moore’s law is upheld.
- Despite of the GPU having higher average values for processor size, TDP, die size and transistors, its average frequency is lower than the average CPU frequency.

![image](https://github.com/user-attachments/assets/5df2f150-ec0f-475a-a3d6-582a3d8fdb1e)

**Intel has been consistent with technology scaling**

## 🌐Future Scope
There are various ways to broaden the examination of CPUs and GPUs:
- Machine Learning and AI-Specific Processors: To evaluate the wider ecosystem of specialised computing hardware, future research could compare with AI-specific processors such as TPUs (Tensor Processing Units) and NPUs (Neural Processing Units).
- Performance vs. Power Efficiency: Future studies should examine the trade-offs between performance and power consumption across CPUs and GPUs, especially for data centres and edge computing applications, as sustainability and energy efficiency become increasingly important factors.
- Impact of Emerging Technologies: A comparative study that considers the emergence of quantum computing and neuromorphic computing may shed light on the areas in which conventional CPUs and GPUs will remain dominant and those in which they might lose ground.
- Real-Time Applications Analysis: Future studies could examine which processor type operates best under circumstances and limitations by examining the distinct roles that CPUs and GPUs play in real-time applications (such as augmented reality and autonomous driving).

## 📚References 

1.	[GPU vs CPU Analysis on Kaggle](https://www.kaggle.com/code/shagundwi/gpu-vs-cpu)
2.	Buber, Ebubekir & Diri, Banu. (2018). Performance Analysis and CPU vs GPU Comparison for Deep Learning. 1-6. 10.1109/CEIT.2018.8751930.
3.	Gregg, Chris & Hazelwood, Kim. (2011). Where is the data? Why you cannot debate CPU vs. GPU performance without the answer. ISPASS 2011 - IEEE International Symposium on Performance Analysis of Systems and Software. 134-144. 10.1109/ISPASS.2011.5762730.
