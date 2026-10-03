# Brakes Required dedicated server

Everything a server operator needs to host a Brakes Required multiplayer
server: release archives, install and update scripts, a configuration
template, a systemd unit, container and hook examples, and the server
directory service. The server itself is the game running without a window
(`--server --headless`); its code lives in the private game repository and is
published here as release assets only.

## Status

No server release exists yet. The first release arrives with Milestone 1 of
the multiplayer work: a headless server with direct connect (address and
port), no lobby, no race results.

## Hosting (preview)

1. Download the latest Linux or Windows server archive from Releases.
2. Unpack it into its own directory, one directory per server instance.
3. Copy `config/server.example.json` to `config/server.json` and set the
   name, port and admin password.
4. Start with `./brakes-required-server --server --config config/server.json`
   or install the systemd unit from `deploy/`.
5. Open the configured UDP port in your firewall. The server must be
   reachable from the outside; players connect outbound.

## Compatibility

| Server release | Client version | Protocol |
| --- | --- | --- |
| none yet | | |

A server and a client only connect when their protocol versions match. The
game shows an update message otherwise.

## Layout

    deploy/     systemd unit, install and update scripts, container example
    config/     server.example.json and its documentation
    hooks/      example scripts run at session start, race start and race end
    directory/  the server directory (list) service and its deployment
    docs/       operating guide

## Related

- Public game builds: https://github.com/Dremet/brakes-required-builds
