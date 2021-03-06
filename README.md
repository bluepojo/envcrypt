# `envcrypt`

`envcrypt` runs commands in a special process environment loaded from encrypted files.

```
$ envcrypt -h
Usage: envcrypt PATH COMMAND...

Set environment variables defined in encrypted file PATH and run COMMAND.

Arguments:
    PATH        path to a gpg-encrypted file that can be read with eg
                `gpg -d PATH`
    COMMAND     command to be invoked in the context of the
                environment defined in PATH
$ echo AWS_ACCESS_KEY_ID=XXXXXXX | gpg -a -e aws.asc
$ envcrypt aws.asc /bin/sh -c 'echo $AWS_ACCESS_KEY_ID'
XXXXXXXX
```

## Install

```
pip install .
```

## Test

```
python setup.py test
```
