# R-Programming-
R-Shiny web application 

ui.R codes
shinyServer(
  pageWithSidebar(
    headerPanel("My first Shiny App"),
    
    sidebarPanel(
      selectInput("Distribution", "Please Selcte Distribution Type",
                  choices =c("Normarl", "Exponential")),
      sliderInput( "sampleSize", "Please select sample size:",
                   min =100, max=5000, value = 1000, step = 100),
      conditionalPanel(condition="input.Distribution == 'Normal",
                       textInput("mean", "Please select the Mean",10),
                       textInput("sd", "Please Select Standard Deviation",3)),
      conditionalPanel(condition = "input.Distribution=='Exponential",
                        textInput("lambda", "Please Select Exponential Lambda:",1))

    ),

    mainPanel(
      plotOutput("myPlot")
    )
    )
)
  
  
