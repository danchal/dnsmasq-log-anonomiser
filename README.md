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
* Anonymises the dns request domain and response ip address logging
* Does not interfere with the dnsmasq process itself
* If input or output files are not explicitely declared then uses stdin / stdout
* Debug log can be sent to separate file, otherwise uses stdout
## References
[dnsmasq](http://www.thekelleys.org.uk/dnsmasq/doc.html)

## Requirements
        Python3
        Dnsmasq

## Usage
Examples

        $ ./dnsmasq-log-anonymiser -i /var/log/dnsmaq.log
        $ tail -f /var/log/dnsmaq.log | ./dnsmasq-log-anonymiser

        optional arguments:
          -h,         --help             show this help message and exit
          -c CONFIG,  --config CONFIG    use a configuration file
          -i INPUT,   --input INPUT      input dnsmasq log file
          -o OUTPUT,  --output OUTPUT    output dnsmasq log file
          -d DOMAIN,  --domain DOMAIN    anonymous domain
          -a ADDRESS, --address ADDRESS  anonymous ip address
          -l LOG,     --log LOG          log to a file
          -v,         --verbose          verbose logging

