<p><img src="http://1000logos.net/wp-content/uploads/2017/07/Logo-Docker-500x394.jpg" alt="docker logo" title="docker" align="right" height="60" /></p>

# Ansible-Cowried
Ansible Role to install and enabling Cowrie-Honeypot inside a Docker.


# Requirements

 - Ansible >= 2.4
 - Docker and docker-py

# Variables
There are a ton of role variables available, most of them around configuring cowrie. See
[defaults/main.yml](defaults/main.yml) for the full list, here are the highlights:

* `cowrie_hostname` is the hostname cowrie should show to things that try to connect. Defaults to
`mgmt01`, just like the default cowrie config.
* `cowrie_port` is set to 2222

All of the default cowrie options can be configured by setting `cowrie_<option>`. Non-default
options go in a dict called `cowrie_settings`. The keys of this dict are the headings in
`cowrie.cfg` and the values are other dicts with key/value pairs of settings. For example, by
default, `cowrie_settings` just configures the json output logging module and looks like this:

```yaml
   cowrie_settings:
       output_jsonlog:
       logfile: "{{ cowrie_log_path }}/cowrie.json"
```

Resulting in the following entry in cowrie.cfg:

```
[output_jsonlog]
logfile: log/cowrie.json
```
## Author Information

You can find me on Twitter: [@itkombinat](https://twitter.com/itkombinat)
