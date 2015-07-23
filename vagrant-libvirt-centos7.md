* To install Vagrant on CentOS refer: https://github.com/LalatenduMohanty/centos7-container-app-vagrant-box/blob/master/docs/quickstart.rst#centos 
* yum install ruby200-ruby-devel
* yum install install gcc-c++
* vagrant plugin install vagrant-hostmanager
* git clone https://github.com/openshift/openshift-ansible.git
* Refer https://github.com/openshift/openshift-ansible/blob/master/README_vagrant.md
* cd openshift-ansible; vagrant up --provider=libvirt --no-provision

```{r}
root@n53 centos]# vagrant plugin install vagrant-hostmanager
Installing the 'vagrant-hostmanager' plugin. This can take a few minutes...
Installed the plugin 'vagrant-hostmanager (1.5.0)'!

[root@n53 centos]# vagrant up
/root/.vagrant.d/gems/gems/fog-core-1.32.0/lib/fog/core/services_mixin.rb:12:in `new': libvirt is not a recognized provider (ArgumentError)
        from /root/.vagrant.d/gems/gems/fog-core-1.32.0/lib/fog/compute.rb:62:in `new'
        from /root/.vagrant.d/gems/gems/vagrant-libvirt-0.0.26/lib/vagrant-libvirt/action/connect_libvirt.rb:38:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/warden.rb:34:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/builtin/config_validate.rb:25:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/warden.rb:34:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/builder.rb:116:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/runner.rb:66:in `block in run'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/util/busy.rb:19:in `busy'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/runner.rb:66:in `run'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:214:in `action_raw'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:191:in `block in action'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:516:in `lock'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:178:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:178:in `action'
        from /root/.vagrant.d/gems/gems/vagrant-libvirt-0.0.26/lib/vagrant-libvirt/provider.rb:70:in `state'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:480:in `state'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:141:in `initialize'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/vagrantfile.rb:75:in `new'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/vagrantfile.rb:75:in `machine'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:614:in `machine'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:168:in `block in with_target_vms'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:192:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:192:in `block in with_target_vms'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:174:in `each'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:174:in `with_target_vms'
        from /opt/rh/vagrant1/root/usr/share/vagrant/plugins/commands/up/command.rb:74:in `block in execute'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:277:in `block (2 levels) in batch'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:275:in `tap'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:275:in `block in batch'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:274:in `synchronize'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:274:in `batch'
        from /opt/rh/vagrant1/root/usr/share/vagrant/plugins/commands/up/command.rb:58:in `execute'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/cli.rb:42:in `execute'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:301:in `cli'
        from /opt/rh/vagrant1/root/usr/share/vagrant/bin/vagrant:174:in `<main>'

```

* Installed https://github.com/fog/fog-libvirt to resolve the above issue

```{r}
[root@n56 c7]# yum install make automake kernel-devel libvirt-devel

[root@n56 c7]# gem install fog-libvirt
Building native extensions.  This could take a while...
rSuccessfully installed ruby-libvirt-0.5.2
Fetching: fog-libvirt-0.0.2.gem (100%)
Successfully installed fog-libvirt-0.0.2
Fetching: multi_json-1.11.2.gem (100%)
Successfully installed multi_json-1.11.2
Parsing documentation for ruby-libvirt-0.5.2
Installing ri documentation for ruby-libvirt-0.5.2
Parsing documentation for fog-libvirt-0.0.2
Installing ri documentation for fog-libvirt-0.0.2
Parsing documentation for multi_json-1.11.2
Installing ri documentation for multi_json-1.11.2
3 gems installed

```

* But still the error abt the "libvirt is not a recognized provider (ArgumentError)" comes

```{r}
[root@n56 openshift-ansible]# vagrant plugin install vagrant-hostmanager
Installing the 'vagrant-hostmanager' plugin. This can take a few minutes...
Installed the plugin 'vagrant-hostmanager (1.5.0)'!


[root@n56 openshift-ansible]# vagrant up --provider=libvirt --no-provision

/opt/rh/ruby200/root/usr/local/share/gems/gems/fog-core-1.32.0/lib/fog/core/services_mixin.rb:12:in `new': libvirt is not a recognized provider (ArgumentError)
        from /opt/rh/ruby200/root/usr/local/share/gems/gems/fog-core-1.32.0/lib/fog/compute.rb:62:in `new'
        from /root/.vagrant.d/gems/gems/vagrant-libvirt-0.0.26/lib/vagrant-libvirt/action/connect_libvirt.rb:38:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/warden.rb:34:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/builtin/config_validate.rb:25:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/warden.rb:34:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/builder.rb:116:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/runner.rb:66:in `block in run'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/util/busy.rb:19:in `busy'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/action/runner.rb:66:in `run'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:214:in `action_raw'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:191:in `block in action'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:516:in `lock'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:178:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:178:in `action'
        from /root/.vagrant.d/gems/gems/vagrant-libvirt-0.0.26/lib/vagrant-libvirt/provider.rb:70:in `state'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:480:in `state'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/machine.rb:141:in `initialize'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/vagrantfile.rb:75:in `new'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/vagrantfile.rb:75:in `machine'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:614:in `machine'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:168:in `block in with_target_vms'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:192:in `call'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:192:in `block in with_target_vms'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:174:in `each'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/plugin/v2/command.rb:174:in `with_target_vms'
        from /opt/rh/vagrant1/root/usr/share/vagrant/plugins/commands/up/command.rb:74:in `block in execute'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:277:in `block (2 levels) in batch'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:275:in `tap'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:275:in `block in batch'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:274:in `synchronize'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:274:in `batch'
        from /opt/rh/vagrant1/root/usr/share/vagrant/plugins/commands/up/command.rb:58:in `execute'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/cli.rb:42:in `execute'
        from /opt/rh/vagrant1/root/usr/share/vagrant/lib/vagrant/environment.rb:301:in `cli'
        from /opt/rh/vagrant1/root/usr/share/vagrant/bin/vagrant:174:in `<main>'
```
