#!/bin/bash


bitcoinrate=$(wget -qO- https://api.coindesk.com/v1/bpi/currentprice/BTC.json | grep -o -P '.{0,0}"USD","rate":".{0,11}' | cut -c 15- | tr -d ,)


mcgriddleprice=$(wget -qO- http://realmenuprices.com/mcdonalds-menu-prices/ | grep -P "Bacon, Egg &amp; Cheese McGriddles<" | grep -o -P '\$.{0,4}' | cut -c 2-)

mcgriddlerate=$(echo "$bitcoinrate/$mcgriddleprice" | bc -l)

printf "The current Bacon, Egg, and Cheese McGriddle to Bitcoin conversion rate is:\n
$mcgriddlerate MCG = 1 BTC"

