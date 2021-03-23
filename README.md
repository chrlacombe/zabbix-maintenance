# zabbix-maintenance - for zabbix

## NAME

zabbix-maintenance - Command-line for zabbix maintenance with disabled triggers

## SYNOPSIS

zabbix-maintenance [OPTION]

## OPTIONS

**--host**=*WORD*\
  Search a host.

**--group**=*WORD*\
  Search all hosts in group.

**--template**=*WORD* (stand-bye problem with API in 4.4)\
  Search all hosts in template.

**--application**=*SPECIFIC PATTERN*\
  Search all hosts a comma separated list of applications.

**--status**=*{0,1}*\
  Apply state 0=enabled 1=disabled.

**--description**=*WILDCARD SEARCH*\
  Search a description to the triggers.

**--hosttags**=*SPECIFIC PATTERN*\
  Search a comma separated list of host tags.

**--triggertags**=*SPECIFIC PATTERN*\
  Search a comma separated list of trigger tags.

**--exclude**\
  Inverse the search

**senderdisable**\
  Specify Sender
  
**--senderkey**=**WORD*\
  Specify item key to send value to. Default value: "trapper.outage". Disable sender if value is empty.

**--sendervalue**=**VALUE*\
  Specify item value. Default value is status value.

-v
Verbose

## AUTHOR

Written by C. LACOMBE

## EXAMPLE

Disable triggers on uq0mt021 with "zab" in description\
./outage --host=uq0mt021 --status=1 --description=zab

Disable triggers on uq0mt021 unless "zab" in description\
./outage --host=uq0mt021 --status=1 --description=zab --exclude

Disable triggers on uq0mt021 with "hosttags:outage" in hosttags\
./outage --host=uq0mt021 --status=1 --hosttags=outage

Disable triggers on uq0mt021 with "triggertags:Cloud & triggertags:Service:MySQL" in triggertags\
./outage --host=uq0mt021 --status=1 --triggertags=Cloud,Service:MySQL

Enable triggers on hosts in DPM_PCL_HAD_BAC group\
./outage --group=DPM_PCL_HAD_BAC --status=0
