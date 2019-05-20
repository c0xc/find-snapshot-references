find-snapshot-references
========================

Find all snapshots that have a reference to a file.
In other words, all snapshots that would have to be deleted
in order to release the space occupied by this file.



Usage
-----

    # find-snapshot-references /data/Share/AUTOCLEAN/cert.pem
    = hourly.7 (/data/Share/.zfs/snapshot/hourly.7/AUTOCLEAN/cert.pem)
    = hourly.17 (/data/Share/.zfs/snapshot/hourly.17/AUTOCLEAN/cert.pem)
    = nightly.0 (/data/Share/.zfs/snapshot/nightly.0/AUTOCLEAN/cert.pem)
    = hourly.10 (/data/Share/.zfs/snapshot/hourly.10/AUTOCLEAN/cert.pem)
    = hourly.0 (/data/Share/.zfs/snapshot/hourly.0/AUTOCLEAN/cert.pem)
    = hourly.4 (/data/Share/.zfs/snapshot/hourly.4/AUTOCLEAN/cert.pem)
    = hourly.14 (/data/Share/.zfs/snapshot/hourly.14/AUTOCLEAN/cert.pem)
    = hourly.13 (/data/Share/.zfs/snapshot/hourly.13/AUTOCLEAN/cert.pem)
    = hourly.9 (/data/Share/.zfs/snapshot/hourly.9/AUTOCLEAN/cert.pem)
    = hourly.3 (/data/Share/.zfs/snapshot/hourly.3/AUTOCLEAN/cert.pem)
    = hourly.1 (/data/Share/.zfs/snapshot/hourly.1/AUTOCLEAN/cert.pem)
    = hourly.11 (/data/Share/.zfs/snapshot/hourly.11/AUTOCLEAN/cert.pem)
    = hourly.16 (/data/Share/.zfs/snapshot/hourly.16/AUTOCLEAN/cert.pem)
    = hourly.6 (/data/Share/.zfs/snapshot/hourly.6/AUTOCLEAN/cert.pem)
    = hourly.2 (/data/Share/.zfs/snapshot/hourly.2/AUTOCLEAN/cert.pem)
    = hourly.8 (/data/Share/.zfs/snapshot/hourly.8/AUTOCLEAN/cert.pem)
    = hourly.18 (/data/Share/.zfs/snapshot/hourly.18/AUTOCLEAN/cert.pem)
    = hourly.12 (/data/Share/.zfs/snapshot/hourly.12/AUTOCLEAN/cert.pem)
    = hourly.15 (/data/Share/.zfs/snapshot/hourly.15/AUTOCLEAN/cert.pem)
    = hourly.5 (/data/Share/.zfs/snapshot/hourly.5/AUTOCLEAN/cert.pem)
    Found file in 20 (out of 115) snapshot(s)

For a deleted file:

    # find-snapshot-references -v -l 3 /data/Share/.zfs/snapshot/nightly.0/AUTOCLEAN/key.pem
    File "key.pem" in /data/Share/.zfs/snapshot/nightly.0/AUTOCLEAN/
    Found root: /data/Share/.zfs
    Parent path: /data/Share/.zfs/snapshot/nightly.0
    Found snapshot dir: /data/Share/.zfs/snapshot
    Relative file path: AUTOCLEAN/key.pem
    Found snapshots (1):
            * nightly.0
    = nightly.0 (/data/Share/.zfs/snapshot/nightly.0/AUTOCLEAN/key.pem)
    Found file in 1 (out of 1) snapshot(s)



Author
------

Philip Seeger (philip@philip-seeger.de)



