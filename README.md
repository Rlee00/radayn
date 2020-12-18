# EPFL ADA 2020 P4 Milestone
## Project by team RadaYN
Data story of socio-emotional interactions on Twitter

## How figures are plotted
Figures are plotted using Plotly Express on Python before being adjusted on Plotly Chart-studio

## How to add figures
1. From Plotly Chart-studio, export html file as zip archive
2. Unzip the file
3. Rename figure.js file as a unique figure file e.g. "graphSetup_uniquefilename.js"
4. Upload the js file and change the first line var to "uniquefilename"
5. In _includes, add "uniquefilename.html" and add the <div id> line, changing the numerical numbers to the "uniquefilename"
6. In _layout, in details.html, copy the script line and change the relevant variable names and add element id
7. In index.md, add figure inline using {% include uniquefilename.html %}
