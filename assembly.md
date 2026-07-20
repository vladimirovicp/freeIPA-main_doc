* https://altlinux.space/korney3g1/libadmix
* https://altlinux.space/korney3g1/freeipa-server-gpo


```bash
cd ./libadmix/
git checkout sisyphus 

gear-hsh

gear-rpm -ba

apt-get install rpm-macros-rust rpm-build-rust python3-dev python3-module-maturin python3-module-pyproject-installer

gear-rpm -ba
```


```
cd freeipa-server-gpo

git checkout -b move_to_admix

gear-rpm -ba

```
