# Viewlog

View logs of each docker container created within this structure.

It works only if you run `./switchLogging on` beforehand to configure logging in all modules and `./server up` to apply the changes to the running docker containers. `viewlog` does not check if you have done that before.

## Syntax

City scope:

```bash
./viewlog [<Country-City>] <modulename> <servicename> [<moreargs>]
```

to view logs of a service in a module of a city.

Chief scope:

```bash
./viewlog chief <servicename> [<moreargs>]
```

to view logs of a service in the main `docker-compose.yml`.

`[<moreargs>]` are optional parameters passed to the underlying call `journalctl`.

## Usage

City scope:

```bash
./viewlog Germany-Hamburg tileserver tileserver
```

to view logs of service `tileserver` in module `tileserver` in city `Germany-Hamburg`.

Chief scope:

```bash
./viewlog chief nginx
```

to view logs of service `nginx` which is one of the chiefs.
