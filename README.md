## Candlestick Pattern Identifier 

The Candlestick Pattern Identifier is a technical indicator I developed using Pine Script for TradingView. 

This indicator is published in Trading View and can be seen here: https://www.tradingview.com/script/BqUM1Jrq-Candlestick-Pattern-Identifier/

## Table of Contents
 
1. [Introduction](#introduction)
2. [How it works](#how-it-works)
    1. [Criteria](#criteria)
    2. [Formulas](#formulas)
3. [Configuration](#configuration)
4. [Features](#features)
5. [Examples](#examples)
    1. [One Candle Pattern](#one-candle-pattern)
          1. [Code for Rising Window](#code-for-rising-window)
          2. [Example of Rising Window in TradingView](#example-of-rising-window-in-tradingview)
    2. [Two Candle Pattern](#two-candle-pattern)
          1. [Code for Bullish Belt Hold](#code-for-rising-window)
          2. [Example of Bullish Belt Hold in TradingView](#example-of-bullish-belt-hold-in-tradingview)
    3. [Three Candle Pattern](#three-candle-pattern)
          1. [Code for Deliberation](#code-for-rising-window)
          2. [Example of Deliberation in TradingView](#example-of-deliberation-in-tradingview)
    4. [Four Candle Pattern](#four-candle-pattern)
          1. [Code for Three Line Strike](#code-for-three-line-strike)
          2. [Example of Three Line Strike in TradingView](#example-of-three-line-strike-in-tradingview)
6. [Acknowledgements](#acknowledgements)
    
## Introduction 

In the investing world, my approach to stock trading would probably have me labeled as a "chartist" as I try to derive as much information I can from a 
stock chart as opposed to other resources like financial documents or news reports. This type of analysis is called "Technical Analysis" and is the core
aspect of my trading strategy. When I began to notice that I missed glaringly obvious signals which could've prevented failed trades, I realized that I 
could avoid this problem entirely by programming tools to automatically perform the analysis on my behalf. The Candlestick Pattern Identifier is 
one of these tools I programmed to asisst me with my stock trading. 

The Candlestick Pattern Identifier is a technical indicator I developed using research by Thomas Bulkowski in his book "Encyclopedia of Candlestick Patterns".
In his research, Bulkowski researched candlestick patterns based on their efficiency and frequency and created a comprehesnive list of top performing patterns 
across both upward and downward markets. When using Bulkowski's research, I created my own set of parameters to look for patterns with high frequency and high percentage of success. 

## How it Works 

### Criteria 

The indicator holds formulas I created for 25 candlestick patterns and outputs them onto a chart in TradingView for any stock across any timeframe.
All candlestick patterns were selected from Encyclopedia of Candlestick Patterns based on the criteria below 

- Probability of success: 66% or higher in up or down markets **(Ensures 2/3 trades made on pattern have a chance of success)**
- Frequency: 10 or higher **(Avoids rare patterns with small sample size)**
- Simplicity: 4 candles or less **(Formulas with increased complexity will create less signals)**

### Formulas

I created formulas using comparison operators on the "open", "close", "high", and "low" properties of a candlestick.

For instance, the formula "green_candle = (open < close)" would flag candles that look like the below. Green candles signify a time period in which the price of a stock went higher. 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/greencandle.png?raw=true" width="100" height="300"></p>

Likewise, the formula "red_candle = (open > close)" would flag candles that look like the below. Red candles signify a time period in which the price of a stock went lower. 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/redcandle.png?raw=true" width="150" height="245"></p>

*Note that the "High" and "Low", regardless of candle properties, are absolutes and will always be above or below the candle body*

## Configuration 

My indicator is published in TradingView's public library and requires no installation. But, a TradingView account is required to utilize all published indicators. 
Account creation is simple and can be done with an accompanying Google or Facebook account as seen below. 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/TRaccount.gif?raw=true" width="640" height="320"></p>

After account creation, click on "Chart" on TradingView's home page.

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/TRstep1.gif?raw=true" width="640" height="320"></p>

Once inside of a chart, click on the "ƒx" icon to open the Indicators & Strategies menu and search for "Candlestick Pattern Identifier".

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/TRstep2.gif?raw=true" width="640" height="320"></p>

## Features 

Disabling and Enabling specific candlestick patterns for strategy optimization and better visibility of the chart: 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/TRFeature.gif?raw=true" width="640" height="320"></p>

Ability to change color, symbol, and location properties of individual indicators to highlight preferred patterns: 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/TRFeature2.gif?raw=true" width="640" height="320"></p>

## Examples 

The examples below are indicators I created for one candle, two candle, three candle, and four candle patterns. I included all relevant declarations 
in the code each example for easier readibility. Patterns designated as "one candle", for example, are patterns that only require one candle to be detected. 

### One Candle Pattern

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/RisingWindowExample.png?raw=true" width="150" height="300"></p>

The Rising window is a one candle pattern with 75% success in markets trending upward and 72% in markets trending downward as per Bulkowski. The defining characteristic of this pattern is that the second candle is significantly above the candle before it. 

##### Code for Rising Window 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/RisingWindowCode.png?raw=true"></p>

The first line shows the declaration for the candle I am looking for, in this case I am looking for green candles (price going up).

The second line defines that the entire candle from yesterday is smaller than the body of today's candle. This was done to strengthen the original 
definition of a rising window and producer stronger and more valid signals. 

The third line defines that the highest point from yesterday is less than the lowest point of today, establishing a gap between the two candles.  

##### Example of Rising Window in TradingView 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/RisingWindowTR.png?raw=true" width="150" height="300"></p>

The picture above shows an example of a Rising Window that my indicator caught in JP Morgan ($JPM) stock. JPM closed at $95.82 the day it was flagged and closed at $101.37 the next day, representing a 5.5% gain. A buy order placed at $95.82 would've made for profitable trade.  

### Two Candle Pattern

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/BullishBeltHoldExample.png?raw=true" width="150" height="300"></p>

The Bullish Belt Hold is a two candle pattern with 71% success in markets trending upward and downward. The "Bullish" in its name represents the sentiment behind this formation as Bullish markets are markets trending upward. The defining characteristics of this are: The current day candle must open below the preceeding day candle and close above the midpoint of the preceeding day candle. 

##### Code for Bullish Belt Hold 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/BullishBeltHoldCode.png?raw=true"></p>

The first line shows the declarations for the candles I am looking for. In this case I'm looking for a red candle from yesterday and a green candle today.

The second line defines that today's close must be greater than or equal to the midpoint of the previous day candle. 

The third line defines that the close must be less than the yesterday's open. This, in combination with the line above, create the upper limit for today's candle as being in between the midpoint and the open of yesteradays candle. 

The fourth line defines that the open of today's candle must be lower than the lowest point of yesterdays candle which defines the lower limit for today's candle. 

##### Example of Bullish Belt Hold in TradingView 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/BullishBeltHoldTR.png?raw=true" width="150" height="300"></p>

The example above is of a Bullish Belt Hold flagged by my indicator in RingCentral ($RNG) stock. RNG closed at $236.51 the day it was flagged and closed at $253.11 the next day, representing a gain of 7.02%. A buy order at $236.51 would've made for a profitable trade. 

### Three Candle Pattern

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/DeliberationExample.png?raw=true" width="150" height="300"></p>

The Deliberation pattern is commonly associated with indecision in the market and the possibility of a reversal, but Bulkowski's research highlights that 
a reversal seldom occurs and that this pattern instead acts as a continaution of the existing trend (77% in upward markets and 75% in downward markets). The defining characteristic of this pattern is progressively smaller and smaller candles. 

##### Code for Deliberation

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/DeliberationCode.png?raw=true"></p>

The first line shows the declaration for the candles I am looking for. In this case, I'm looking for green candles going back as far as two days ago. 

The second line defines that the body of the candle two days ago is larger than the one one day ago. The third line defines that the body of the candle one day
ago is larger than the candle today. Both of these lines establish the progression of smaller and smaller candles. 

The third and fourth line define that the high point of the preceeding day candle is lower than the low point of the candle after it. This is done from the candle two days ago to the candle today to establish the uptrend. 

##### Example of Deliberation in TradingView 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/DeliberationTR.png?raw=true" width="150" height="300"></p>

The example of the Deliberation pattern above was flagged by my indicator in Las Vegas Sands ($LVS) stock. The uptrend halted for two days after the 
pattern was flagged but continued to climb higher. The price of LVS shares were $64.15 the day it was flagged and $68.70 at the very last candle which represents a gain of approximately 7% and would've made for a profitable trade. 

### Four Candle Pattern

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/ThreeLineStrikeExample.png?raw=true" width="150" height="300"></p>

The Three Line Strike, commonly known as a continaution pattern, is actually defined as a reversal pattern according to Bulkowski with 65% success in upward markets and 83% in downward markets. The defining characteristic of this pattern is that the most recent candle complete engulfs the preceeding three candles. 

##### Code for Three Line Strike 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/ThreeLineStrikeCode.png?raw=true"></p>

The first line shows the declaration for the candles I am looking for. In this case, I'm looking for three green candles preceeding a red candle. 

The second, third, and fourth line establish the uptrend by stating that the close of the preceeding day is less than open of the day after. 

The fifth line defines the condition for the most recent candle to be much larger than the three candles prior to it by stating close of today's candle is lower than the open of the candle from three days ago. 

##### Example of Three Line Strike in TradingView 

<p align="center"><img src="https://github.com/Rsiriy/Pine-Script-Stock-Trading-Scripts/blob/master/images/ThreeLineStrikeTR.png?raw=true" width="150" height="300"></p>

Above is an example my indicator caught in Zoom Video Communications Inc. ($ZM) stock. ZM closed at $260.30 the day it was flagged and dropped to $246.54 four days later. A sell order at $260.30 would've made for a profitable trade. 

## Acknowledgements

The research by Thomas Bulkowski in his book "Encyclopedia of Candlestick Patterns" was essential in the creation of this indicator. 
