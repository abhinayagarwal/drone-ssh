Use the SSH plugin to execute commands on a remote server. The following parameters are used to configure this plugin:

* `host` - address or IP of the remote machine
* `port` - port to connect to on the remote machine
* `user` - user to log in as on the remote machine
* `commands` - list of commands to execute

The following is a sample SSH configuration in your .drone.yml file:

```yaml
deploy:
  ssh:
    host: foo.com
    user: root
    port: 22
    commands:
      - echo hello
      - echo world
```

The plugin authenticates to your server using a per-repository SSH key generated by Drone. You can find the public key in your repository settings in Drone. You will need to copy / paste this key into your `~/.ssh/authorized_keys` file on your remote machine.