---
title: "Getting Started"
date: "March 4th, 2019"
author: "Kyle Barrett"
header-includes: \usepackage{amsmath}
output:
  html_document:
   mathjax: "http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
   number_sections: true
params:
  set_title: "Mathematical Model for Anaerobic Digestion in Batch Reactor"
runtime: shiny
theme: cerulean
---

<style>
body {
text-align: justify}
</style>

<style type="text/css">

body{ /* Normal  */
      font-size: 15px;
  }
td {  /* Table  */
  font-size: 14px;
}
h1.title {
  font-size: 38px;
  color: DarkRed;
}
h1 { /* Header 1 */
  font-size: 26px;
  color: DarkBlue;
}
h2 { /* Header 2 */
    font-size: 19px;
  color: DarkRed;
}
h3 { /* Header 3 */
  font-size: 22px;
}
code.r{ /* Code block */
    font-size: 13px;
}
pre { /* Code block - determines code spacing between lines */
    font-size: 14px;
}
</style>

## **Quick Summary** 

Navitage to the `Plots` or `Tables` tab on the left, and then adjust `Model Parameters` to see their effect on the overall process. Note that not every parameter will have an effect on every plot.

## **Purpose** 

This app is associated with my senior design project in chemical engineering at Drexel University. [^1]
The model was developed to simulate the degradation of heavy organic compounds through anaerobic digestion. Five unique processes take place in the simulated batch reactor, including the enzymatic hydrolysis of guar gum, acidogenesis of polysaccharide chains, acetogensis, methanogenesis, and anaerobic degredation using bacteroides. See the `Background of Process` tab for a more detailed process description.
<br><br>
# **Introduction and Motivation**

In the pursuit of energy independence in the United States and abroad, hydraulic fracking is an increasingly popular method of natural gas extraction. As the popularity of this particular form of drilling increases, some of the negative impacts of the process are starting to manifest as well. The primary impact that most people hear about is the contamination of drinking water supplies on or near fracking sites. The goal of this project was to develop a system that is able to remove the contaminants left in the water affected by the fracking process. A batch anearobic bioreactor is the second out of four units in the developed PFD, and was modeled using kinetic parameters found in the literature. The model simulates the degredation and conversion of the contaminants into biogas (*$CO_{2}$*, *$H_{2}$*, and *$CH_{4}$*). 
<br><br>
The Contaminants being degraded in this unit include:

  * **Guar Gum** *(Done)*
  * **PEG-400** *(Done)*
  * Petrolium Distillates
  * Methanol *(Research Stage)*
  * Isopropanol *(Research Stage)*

<br>
# **What the App Does**


The purpose of this app is to optimize the model parameters in order to increase the profitability of the bioreactor. The user will be able to adjust initial bacteria concentrations, reactor temperature (both static and dynamic), etc., and see a visual representation of the outcome. Note that not all adjustable parameters will have an effect on every plot.

As soon as the user loads the app, the model is compiled and run using the current parameter settings. As the user adjusts these parameters, the plots and tables will update according to the new settings once the **Resimulate** button has been clicked (This button is on each of the table and plot tabs).

The tabs on the left then allow the user to navigate the simulated reactor output and read more about the process. You can also specify the time in which to truncate the data and evaluate the output, though the minimum value is currently 100 h. The reactor that follows the anaerobic digestor is capable of removing small quantities left over. Ideally you would set a minimum acceptable concentration, and optimize parameters to decrease the time required to reduce the contaminants to that concentration, though this not been implemented due to the lack of observational data.

<br>
# **Side Tabs**


  * Use the `Model Parameters` tab to adjust the model inputs. Clicking a category will open a separate menu with adjustable parameters. Click the category again to make the menu disappear. The `simulation` option will allow for a sensitivity analysis of a chosen parameter.

  * Use the `Plots` tab to view a specific set of plots. Selections include *Main Components*,  *Intermediate Products*,  *Bacteria Growth*, and *Reactor Properties*.

  * Use the `Tables` tab to view the input and output concentrations. Selections include *Main Components*  and *Reactor Properties*.
 
  * Use the `Codes` tab to display and download the model file, <tt>AnaerobicDigestionShiny.cpp</tt>, or the <tt>app.R</tt> used for this application. Note that other scripts are needed to run the model.

  * Use the `Mathematical Model` tab  to display the differential equations present in the model.
  
  * Use the `Background of Process` tab to download a PDF summarizing the model process.


## **Features Coming Soon** 

  * Addition of petrolium distillates, methanol, and isopropanol to the model
  * Temperature Optimization --> most likely piecewise function
  * Visual Representation of model
  
## **Potential Upcoming Features** 

  * Expected Revenue Plots
  * Optimization of other reactor settings
  
<br>
[^1]: Credit:

    Year: 2019, Team Name: "Frack Off", Model/App Developer: Kyle Barrett
    Group Members: Kyle Barrett, Luke Growney, Prem Patel, Farhaan Rizvi
