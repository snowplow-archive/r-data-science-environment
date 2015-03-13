# R Data Science environment

VM with complete R (RStudio) environment. Setup an R environment without any faff.

## Quickstart

Assuming git, [Vagrant] [vagrant-install] and [VirtualBox] [virtualbox-install] installed:

```
 host$ git clone https://github.com/snowplow/r-data-science-environment.git
 host$ cd r-data-science-environment
 host$ vagrant up
```

This will launch a VM, install on it [R][r] and [R Studio Server][rstudioserver], and start R Studio Server. You then simply navigate your browser to:

```
http://localhost/8787
```

Log in with

```
username: rsuser
password: rspword
```

And get data crunching...

## Notes

R is a RAM hungry program - this VM has been built on the basis it is run on a host with 16GB of RAM. (It takes 10GB for the VM.)

To adjust the amount of RAM used, update the following line in the `Vagrantfile` prior to executing `vagrant up`:

```bash
    vb.memory = 10240
```

[vagrant-install]: http://docs.vagrantup.com/v2/installation/index.html
[virtualbox-install]: https://www.virtualbox.org/wiki/Downloads
[r]: http://cran.r-project.org/
[rstudioserver]: http://www.rstudio.com/products/rstudio/download-server/