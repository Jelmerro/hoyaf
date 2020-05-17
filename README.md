Horsemen of your altered future
===============================

#### Block the four horsemen and other companies permanently using routing tables

## A New World

- Fetches the list of ip ranges from ipinfo.io for a defined list of companies
- Redirect all ip ranges to 127.0.0.1 to prevent a connection
- Enable or disable ip ranges in bulk for a single or all included companies
- Block any other company that has an Autonomous System Number (ASN) on ipinfo.io

## Alter your future

Hoyaf has two optional arguments to block, which can be repeated as needed:

- `-b <name>` / `--block <name>` to add a range of addresses to the routing table.
- `-u <name>` / `--unblock <name>` to add a range of addresses to the routing table.

For both options, the name can be: `all`, a company name, or a custom ASN.

Two other options are present in hoyaf:

- `-l` / `--list` to show a list of currently blocked companies (as far as hoyaf knows)
- `-h` / `--help` to show the usage summary, similar to this paragraph

The fastest way to ban all included companies:

```
./hoyaf -b all
```

This will without a doubt cause many familiar sites to break, or even be unreachable.
It can always be completely reversed with `./hoyaf -u all`.
Cherry-picking the companies that you don't want to deal with is recommended.

## Some Context

This project is inspired by
[wesaphzt's project to block all Google ip's](https://github.com/wesaphzt/block-all-google).
Hoyaf expands on this to also block other big companies and contains an improved cli interface.
The name is inspired by the [Four Horsemen](https://en.wikipedia.org/wiki/Four_Horsemen_of_the_Apocalypse),
a common name for [Big Tech](https://en.wikipedia.org/wiki/Big_Tech) companies.
Other terms are inspired by the great King Gizzard & the Lizard Wizard album named
[Murder of the Universe](https://en.wikipedia.org/wiki/Murder_of_the_Universe).
Finally thanks to [ipinfo.io](https://ipinfo.io) for providing the ip range lists.

Hoyaf is written in bash and uses curl, proxychains and tor to fetch the ip ranges.

## Alter Me

Released into the public domain under the terms of the [UNLICENSE](./UNLICENSE).
