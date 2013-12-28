Variomedia DNS updater
======================

Shell script for updating DNS entries via Variomedia’s HTTP API (dynamic DNS). 
See <https://dyndns.variomedia.de/>.

Basically, it compares your current WAN address to a given FQDN DNS entry. If 
they differ, it calls Variomedia’s HTTP API and updates all entries specified in 
its config file.

Requirements
------------

- `bash`
- `curl`
- `dig`

config file variables
---------------------

<dl>
  <dt>hostname</dt>
  <dd>FQDN to test the WAN address against.</dd>
  <dt>domains</dt>
  <dd>FQDN of the domains to modify.</dd>
  <dt>username</dt>
  <dd>Your dynamic DNS username (= account email address).</dd>
  <dt>password</dt>
  <dd>Your dynamic DNS password password.</dd>
  <dt>site</dt>
  <dd>(optional) Web site to check for your WAN IP. Must return the IP in the 
  response body, _not_ through fancy javasrcipt.</dd>
</dl>

Usage
-----

Copy `nsupdate.conf.sample` to `nsupdate.conf` and fill in your details. Then 
run `bash variomedia-dns-updater.sh`. You can also copy the config file name to 
somewhere else and supply it via the `-c` swtich.

Contributing
------------

I am using nvie’s
[git branching model](http://nvie.com/posts/a-successful-git-branching-model/ 
"nvie.com: A successfull Git branichng model"). To contribute you should follow 
these steps:

0. Check if your proposed change is already implemented in the `develop` branch
1. Fork the repository on Github
2. Create a named feature branch (like `feature-x`)
3. Write your change
4. Submit a Pull Request against the `develop` branch using Github

License and Authors
-------------------

Authors: ka’imi <kaimi@kaimi.cc>
