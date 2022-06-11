---
layout: post
title:  "Prueba video"
date:   2016-03-15
excerpt: "Custom written post descriptions are the way to go... if you're not lazy."
project: true
tag:
- sample
- post
- video
comments: true
---
~~~~~~~~
#!/bin/bash

if [ -z "$1" ]
then
        echo -e  "\e[33m[*]-Use: ./nmapScan\e[0m" "\e[31m[<IP>]\e[0m"
        exit 1
fi

printf "\n[*] Puertos Abiertos:\n\n" > OpenPorts

echo -e "\e[31m Escaneando Puertos Abiertos...\e[0m"

sudo nmap -sS -p- --open --min-rate 5000 $1 -n -Pn | tail -n +5 | head -n -3 >> OpenPorts

cat OpenPorts