# acdul

Let Transmission and HaH upload completed torrent to Amazon Cloud Drive.

## Requirements

Only supports Python 3.5 or later.

You have to setup acd_cli first.

Modify Transmission settings:

```json
{
    "script-torrent-done-enabled": true,
    "script-torrent-done-filename": "/path/to/scripts/notify.sh",
}
```

Transmission must be able to execute the script, watch out permission problem.

Look `acdul.example.yaml` and create your own configuration.

## Run Daemon

```shell
python3 -m acdul --settings=tmacd.yaml
```

## RESTful API

### POST /torrents

Upload all completed torrents.

200 - a list of torrent ID, in JSON

### PUT /torrents/{ID}

Upload torrent by ID.

204 - success
400 - invalid torrent ID
