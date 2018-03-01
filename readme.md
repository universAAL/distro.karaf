# Quickstart

1. download, or clone, https://github.com/universAAL/distro.karaf `git clone https://github.com/universAAL/distro.karaf`. Notice this will checkout the latest development version, if you want to use a specific version of universAAL check out one the the tags `git checkout <version>`
2. maven install it `cd distro.karaf` `mvn install`
3. `cd target/assembly` run `bin/karaf` (use the .bat or the .sh according to your Operative System) 
4. this will start universAAL middleware by default. To add specific components use the command `feature:install <name_of_component>`, you may find the full list of components by running the command `feature:list | grep universAAL` (please find the documentation about the functions each provide and how to configure each on our wikis)
5. you may add your modules (a.k.a. bundles) to the _deploy_ folder, this will automatically launch them. As an alternative you can create your own [karaf features](https://karaf.apache.org/manual/latest/provisioning)

## Quick Notes
You may redistribute by zipping the whole _assembly_ folder, or using the provided compressed files (for which you'll probably need to to do some changes to the configuration files to get to the desired state).

To reset the container: delete the _data_ folder; alternativelly add `clean` to the launching command (which just deletes the _data_ folder automatically)

Karaf can be runned as background service by using the `start` and `stop` scripts instead of the `karaf` script. To access command line to background karaf service launch the `client` script.

To configure your own distribution we recommend to fork this repository and provide your configuration in the _src/main/filtered-resources_ (as if this where you root karaf folder). Please read about [karaf](https://karaf.apache.org/manual/latest/) to get the best result.
