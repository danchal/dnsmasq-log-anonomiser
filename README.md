# Dnsmasq Log Anonymiser

A command line tool to anonymise the log of dnsmasq in real time.

#### Before

        Mar  5 00:00:36 dnsmasq[5347]: 30997 192.168.0.128/55189 query[A] google.com from 192.168.0.128
        Mar  5 00:00:36 dnsmasq[5347]: 30997 192.168.0.128/55189 forwarded google.com to 8.8.8.8
        Mar  5 00:00:36 dnsmasq[5347]: 30997 192.168.0.128/55189 reply google.com is 216.58.201.110

#### After

        Mar 5 00:00:36 dnsmasq[5347]: 30997 192.168.0.128/55189 query[A] example.com from 192.168.0.128
        Mar 5 00:00:36 dnsmasq[5347]: 30997 192.168.0.128/55189 forwarded example.com to 8.8.8.8
        Mar 5 00:00:36 dnsmasq[5347]: 30997 192.168.0.128/55189 reply example.com is 0.0.0.0

## Features

## References
[dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html)

## Requirements
        Python3
        Dnsmasq

## Usage

        optional arguments:
          -h,         --help             show this help message and exit
          -c CONFIG,  --config CONFIG    use a configuration file
          -i INPUT,   --input INPUT      input dnsmasq log file
          -o OUTPUT,  --output OUTPUT    output dnsmasq log file
          -d DOMAIN,  --domain DOMAIN    anonymous domain
          -a ADDRESS, --address ADDRESS  anonymous ip address
          -l LOG,     --log LOG          log to a file
          -v,         --verbose          verbose logging

