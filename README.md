## Candlestick Pattern Identifier 

The Candlestick Pattern Identifier is a technical indicator developed using Pine Script for TradingView. 

## Table of Contents

- [Introduction](#introduction)
- [How it Works](#features)
- [Examples](#feedback)
- [Installation](#Installation)

## Introduction 

In the investing world, my approach to stock trading would probably have me labeled as a "chartist" as I try to derive as much information I can from a 
stock chart as opposed to other resources like financial documents or news reports. This type of analysis is called "Technical Analysis" and is the core
aspect of my trading strategy. When I began to notice that I missed glaringly obvious signals which could've prevented failed trades, I realized that I 
could avoid this problem entirely by programming tools to automatically perform the analysis on my behalf. The Candlestick Pattern Identifier is 
one of these tools I programmed to asisst me with my stock trading. 

The Candlestick Pattern Identifier is a technical indicator I developed using research by Thomas Burkowski in his book "Encyclopedia of Candlestick Patterns".
In his research, Burkowski researched candlestick patterns based on their efficiency and frequency and created a comprehesnive list of top performing patterns 
across both Bull (upward market trend) and Bear (downward market trend) markets. When using Burkowski's research, I created my own set of parameters to look for
patterns with high frequency and high percentage of success. 

## How it Works 

##### Criteria 

The indicator holds formulas I created for 25 candlestick patterns and outputs them onto a chart in TradingView for any stock across any timeframe.
All candlestick patterns were selected from Encyclopedia of Candlestick Patterns based on the criteria below 

- Probability of success: 66% or higher in Bull or Bear markets (Ensures 2/3 trades made on pattern have a chance of success)
- Frequency: 10 or higher (Avoids rare patterns with small sample size)
- Simplicity: 4 candles or less (Formulas with increased complexity will create less signals)

##### Formulas


## Examples 

## Installation 
