freebsd-ports
=============

My FreeBSD ports, most of which should end up upstream at one point or another

# Current packages in this repository

## luaevent

- Builds / installs cleanly
- Tests work
- Prosody (my consuming application that I built the port for..) fails to start

Open, to be investigated

## luadbi

- Builds / installs cleanly
- Needs options (currently always builds against all free DBs,
  MySQL/PostgreSQL/sqlite)
- Untested

# Future plans

- Option for prosody: Depend on luajit
