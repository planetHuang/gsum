# gsum
GSum: A General Graph Summarization Framework by Finding Homogeneous Structures

contact: jgyou at 126.com

# run
The code works under Windows with Visual Studio or Cygwin with GCC, Mac OS X, Linux and other Unix variants with GCC. Make sure that a C++ compiler is installed on the system. Visual Studio project files and makefiles are provided. For makefiles, compile the code with “make all”. The code uses the SNAP (http://snap.stanford.edu/) as its base graph processing lib.

Note: To visualize the result graph, GraphViz should be installed and the path should be set. Note that for some graphs with big number of nodes, GraphViz may result in the error of memory overflow. But it still works for not that big graphs.

/////////////////////////////////////////////////////////////////////////////  
Parameters:  
-i:Input undirected graph (single directed edge per line) (default:'BPExample’)  
-k:Input the number k of node groups/clusters (default:2)  
-o:Output file name prefix (default:'')  
-v:Verbose (Whether print the intermediate info) (default:F)  
-m:Method. Choose a graph summary method, EN: Entropy-based summary; MDL: MDL-based summary. (default:'EN')  
-sm:Submethod. Choose an entropy-based graph summary sub-method. E: by entropy; EG: by entropy gain; EGH:by entropy gain heap. (default:'EGH')  
-cm:Choose initial coloring method. ByCnCom: Coloring graph by connected components; ByRandom: Coloring graph by random. (default:'ByCnCom')  
-t:Output file type. 0:output node groups; 1:output type 0 + output summarized graph; 2:output type 1 + output entropy spectrum, reconstruction error; 3:output type 2 + output original graph with node group colored (default:1)  
-v:Whether print the intermediate info (default:'F')  
-rd:Whether redirect the console to the output file (default:'F')  
-p:Prune ratio (default:0)  


/////////////////////////////////////////////////////////////////////////////  
Usage:  
$gsum -i:MDLExample -k:4 -v:T

$gsum -i:BPExample -k:4 -v:T -rd:T

$gsum -i:CaveExample -k:3 -v:T -rd:T

$gsum -i:datasets\bp2cave.txt -k:7 -v:T -rd:T -m:EN -sm:EGH

$gsum -i:datasets\email-Eu-core.txt -k:42 -v:T -rd:T -m:EN -sm:E

$gsum -i:com-dblp.ungraph.txt -k:100 -rd:T -m:EN -sm:EGH

$gsum -i:datasets\dblp2new.txt -k:100 -rd:T -m:EN -sm:EGH


Note for some examples:  
MDLExample  
/* the nodes is 8, the edges is 11  
1:  2 3 5 7 8  
2:  3 1  
3:  1 2  
4:  8  
5:  7 8 1  
6:  7 8  
7:  1 5 6  
8:  1 4 5 6  
*/  

BPExample  // int LeftNodes = 50, RightNodes = 100, Edges = 4000;

CaveExample  // int LeftNodes = 10, MiddleNodes = 20, RightNodes = 30;  //diagonal block

bp2cave.txt  // the nodes is 140, the edges is 1430

email-Eu-core.txt  // the nodes is 1005, the edges is 25571

com-dblp.ungraph.txt  // the nodes is 317080, the edges is 1049866
