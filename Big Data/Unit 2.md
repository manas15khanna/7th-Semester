# Architecture Components 
```mermaid 
%%{
init: {
'theme': 'base',
'themeVariables': {
'primaryColor': '#1e1e1e',
'primaryTextColor': '#ffffff',
'primaryBorderColor': '#444444',
'lineColor': '#888888',
'nodeBorder': '#444444',
'mainBkg': '#1e1e1e',
'defaultLinkColor': '#888888',
'fontFamily': 'ui-monospace, monospace'
}
}
}%%
flowchart 
A[Large Data] ==> B[Divide into Parts]
B --- C1[C1] 
B --- C2[C2]
B --- C3[C3]
B --- C4[C4] 
C1 --- P1[Process]
C2 --- P2[Process]
C3 --- P3[Process]
C4 --- P4[Process]
P1 ==> C[Combine Results]
P2 ==> C[Combine Results]
P3 ==> C[Combine Results]
P4 ==> C[Combine Results]
C ==> O[Output]
```
Each computer has it's own CPU, memory and storage. 
## Advantages 
- Processing happens at the same time 
- Handle Large amount of Data
- Can easily add more computers. 
## Disadvantages 
- High Cost 
- High Complexity 
# Unstructured Data Analytics 
- UDA is a process of collecting processing and analyzing unstructured data to extract useful information, patterns and insights. 
- Since unstructured data is complex, technologies such as AI/ML, NLP & BigData are used for analysis. 
- UDA is a process of analyzing data such as text, image, video, audio to obtain meaningful information. 
- UDA is basically used to improve business decisions, detect fraud, predict trends, enhance customer service, understand customer opinion, etc.
## Steps 
1. Data Collecting
2. Data Storage 
3. Data Processing 
4. Data Analysis
5. Data Reporting 
