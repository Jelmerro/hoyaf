Horsemen of your altered future
===============================

#### Block the four horsemen and other companies permanently using iptables

## A New World

- Fetches the list of ip ranges from whois.radb.net for any ASN
- Drops all packets to any of the ips in the ranges
- Checks and aggregates rules before adding them
- Enable or disable ip ranges in bulk for a single or all included companies
- Block any other company that has an Autonomous System Number (ASN)
- Persistent across reboots thanks to iptables-save (last line of the script)

## Alter your future

Hoyaf has two optional arguments to block, which can be repeated as needed:

- `-b <name>` / `--block <name>` to add a range of addresses to iptables.
- `-u <name>` / `--unblock <name>` to remove a range of addresses from iptables.

For both options, the name can be: `all`, a company name, or a custom ASN.

Three other options are present in hoyaf:

- `-r` / `--refresh` to request the ip ranges again, even if they are cached
- `-l` / `--list` to show a list of currently blocked companies (as far as hoyaf knows)
- `-h` / `--help` to show the usage summary, similar to this paragraph

The simplest way to ban all included companies:

```
./hoyaf -b all
```

This will without a doubt cause many familiar sites to break, or even be unreachable.
Included companies can also be unblocked in bulk with `./hoyaf -u all`.
Cherry-picking the companies that you don't want to deal with is recommended.
Companies that were manually blocked are not included in the 'all' option,
but they are visble in the list of currently active rules: `./hoyaf -l`.

## Some Context

This project is inspired by
[wesaphzt's project to block all Google ip's](https://github.com/wesaphzt/block-all-google).
Hoyaf expands on this to also block other big companies and contains an improved cli interface.
The name is inspired by the [Four Horsemen](https://en.wikipedia.org/wiki/Four_Horsemen_of_the_Apocalypse),
a common name for [Big Tech](https://en.wikipedia.org/wiki/Big_Tech) companies.
Other terms are inspired by the great King Gizzard & the Lizard Wizard album named
[Murder of the Universe](https://en.wikipedia.org/wiki/Murder_of_the_Universe).

Hoyaf is written in bash and uses whois, proxychains and tor to fetch the ip ranges.
The ranges are then blocked using iptables.
If you want to combine [vpn_or_bust](https://github.com/Jelmerro/vpn_or_bust) with hoyaf,
make sure to run vpn_or_bust first.
If the rules are not persistent when rebooting,
check if the iptables location at the end of the program is correct for your linux distribution.

## Alter Me

Released into the public domain under the terms of the [UNLICENSE](./UNLICENSE).
