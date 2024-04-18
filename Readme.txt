1.System requirements
-------------------------
a. We implemented the codes with MATLAB R2022a on Windows10.

2.Document description:
-------------------------
program：
	Dataset 1 program: Files for processing and analyzing Dataset 1
	Dataset 2 program: Files for processing and analyzing Dataset 2
	bar_plot.m : Main script for drawing clustered grouped histograms
	bar_figure.m : Function to draw clustered grouped histograms
	net1.gephi ：Gephi project file to draw the gene network diagram of data set 1
	net2.gephi ：Gephi project file for drawing the gene network diagram of data set 2
	barplot.m : Main script for drawing clustered grouped histograms
	bar_figure.m : Function to draw clustered grouped histograms
	BarHPlot.m: Function to draw horizontal histogram
	psortBar.m：The main script to draw a histogram of the average p value of each gene combination
	FilledPlot3.m：Function to draw a three-dimensional filled line chart
	t_FilledPlot3.m：Script to draw three-dimensional filled line chart of gene expression (TPM) of each sensitive gene
	SankeyChart.m：Functions that draw Sankey diagrams
	SankeyPlot.m：Script to draw a Sankey diagram of the relationship between sensitive genes and diseases
	data.xlsx：A table that stores the data required for a Sankey diagram

	The main difference between Dataset 1 program and Dataset 2 program lies in the different input data sets. The following sub-file description applies to the aforementioned two files:
	-------------------------
	Merged data:Two datasets that hold the raw data
	
	Data preprocessing:
		preprocess1.m ：The main script for data preprocessing
		p_data.mat ：A data preprocessing function that includes the average processing of 0 values and the moving average processing of the original data
		t.mat ：Post-processing data obtained after data preprocessing
		sample_2.xlsx, sample_3.xlsx：Collated raw data

	kmeans++:
		kmeans_plusplus1.m：kmeans++ algorithm script 
		transition.m ：The gene expression time series is transformed into a function of gene dynamics (gene expression distribution)
		setHandel.m ：A function to set the drawing window size
		outpng.m ：A function that outputs a picture

	Build a gene network:
		process2.m ：The main script for building gene networks
		corrplot.m ：A function used to plot the correlation coefficients
		pre.mat ：The corresponding results of constructing gene network scripts

	Identify sensitive genes and gene combinations：
	Initial network entropy index calculation:
		c_index0.m：A script to calculate the initial network entropy
		refine_Main_ARNN.m：ARNN function
		NN_F2.m：The function that is required to process the data in the ARNN algorithm prediction process
		Stem3D.m：A function for drawing 3D stem diagrams
		error.mat：ARNN prediction error saved after running
		init_index.mat：The initial overall network entropy of the output

	Disturbance handling:
		raodong_point.m ：A script that perturbs each gene to different degrees and determines whether there is a significant impact on the system after perturbation
		Butterfly.m ：A function for drawing butterflies
		StackedButterflyPlot.m ：A function that draws a stacked butterfly diagram
		point_result.mat ：The result of output from script raodong point.m after perturbation processing

	Subnetwork exploration:
		final_test.m ：Generate subgraph vertex combination to do the perturbation processing and identify its influence and function script
		net_train.m ：Calculate the function of generating the initial network entropy index of the subgraph
		final_result.mat：The result of the final test.m script
	Draw gene subnetworks:
		Gplot.m：Script to draw gene subnetworks
picture:
The sub-documents collated the images produced in the study
	Dataset1：All pictures about dataset 1
	Dataset2：All pictures about dataset 2
	Figures included in functional analysis：Pictures from gene functional analysis
	Organized pictures：The big pictures obtained by integrating the pictures in Dataset1 and Dataset2

3.Use script sequence：
-------------------------
preprocess1.m-->kmeans_plusplus1.m-->process2.m -->c_index0.m-->raodong_point.m-->final_test.m 
Note:  The .mat files in different folders are needed to updat during operation.
	
