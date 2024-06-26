# Crypto Tax Calculator (BETA-WiP)

Cryptocurrencies Profit/Losses Calculator for the following plattforms:

- Kraken
- Coinbase
- Numerai

Calculates profit/loss for buy/sell orders (FIFO method) of cryptocurrencies and stake/earn profits. It also takes into account the difference in price of the earn/staked profits and the sell orders.

The kraken trades export does not contain the actual prices for the earn profits. The price is queried against the [Kraken Rest API](https://docs.kraken.com/rest/#tag/Spot-Market-Data/operation/getOHLCData). You can use a file with the prices instead. If not, a excel file will be created with the prices/exact dates used. By default: ``data/stake_prices.xlsx``

## Disclaimer
This project, code, procedures and results are not to be regarded as financial, accounting or tax advise for your country!

## LOP/WiP
- Calculate taxes based on % of profit
- Load list of id's to exclude from calculation

## Flaws (Maybe in future LOP)
- Only EUR
- Only EURvsCrypto trades are taken into account (Not trades between different cryptocurrencies)
- Only Buy/Sell/Earn or Payouts/Burns orders are considered.

## Installation
Prerequisites: git and Python.

1. Clone the repository
2. Install its dependencies via ``pip install -r requirements.txt``

## Run
1. Export your orders from the exchanges as ``.csv`` format in the ``data/`` folder with the default names or specify the path in the options. See Below.
2. ``python run.py`` . Note that there are options which you can specify, see below.
3. Check the outputs in ``data/export/`` if you exported the data. 

## Options
You can specify different options as arguments:

- ``--year`` - Select for which year you want the calculations. By default all years are reported.
- ``--plattform`` - Select the exchange: ``kraken``,``coinbase`` or ``nmr``. Multiple exchanges separated by ','. By default all three exchanges are used. 
- ``--export`` - Export the data in excel format in the ``data/export/`` folder: Result + one file per cryptocurrency. 
- ``--coinbase_file`` - Specify the path for the coinbase export file.
- ``--kraken_file`` - Specify the path for the kraken export file.
- ``--nmr_file`` - Specify the path for the Numerai export file. - WiP
- ``--price_file`` - Specify the file containing the prices for the missing stake information.

## Example

``python run.py --year 2023 --kraken_file "data/kraken.csv"``

## Participate

This is an open source project and you are invited to participate. If you find a bug do not hesitate to submit and issue or even fix it yourself and make a pull request.

## IMPORTANT: Check the results before submitting the information to the tax authorities!!

