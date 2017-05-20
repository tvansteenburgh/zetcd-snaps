# zetcd-snaps
Snapcraft.yaml for building [zetcd](https://github.com/coreos/zetcd) snap packages

## Building

In the root of the repo run:

```bash
snapcraft cleanbuild
```

## Installing from the Ubuntu Store

```bash
snap install zetcd --edge
```

## Running

Forward ZooKeeper requests on `:2181` to an etcd server listening on
`localhost:2379`:

```bash
zetcd --zkaddr 0.0.0.0:2181 --endpoints localhost:2379
```

Simple testing with `zkctl`:

```bash
zetcd.zkctl watch / &
zetcd.zkctl create /abc "foo"
```
