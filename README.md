# minecraft-playbook
Create a minecraft server in the CLC cloud

### DESCRIPTION:
This playbook will provision a Minecraft game server with public IP address in the Centurylink Cloud. The public address only supports 80 for the time being. The high level tasks are as follows:
* provision a group, server, and public IP (single Ubuntu 14.04 x64)
* installs java
* configure environment for minecraft
* propogates minecraft configs
* installs and starts minecraft
* prints the word "Profit"...because it's fun

### DEPENDENCIES
* Place your public key in the 'keys/ssh-rsa-key.pub' file
* Kind of important to have an account in the CLC Cloud
* Pass --extra-args alias variable

### TYPICAL OVERRIDES:
* group_name: group in CLC the server will live under, gets provisioned if isn't present (default == Minecraft)
* server_name: base name of server [can only be 6 characters or less] (default == MCRAFT)
* datacenter: locate to provision servers (default == WA1)
* minecraft_user: user to install minecraft on the server (default == minecraft)
* minecraft_group: group to install minecraft on the server (default == minecraft)
* minecraft_server_version: version to install (default == 1.8.7)
* minecraft_java_opts: options for java [heap, garbage collection, threads, etc] (defaults == -Xmx1G -Xms1G -XX:+UseConcMarkSweepGC -XX:+CMSIncrementalPacing -XX:ParallelGCThreads=2)
* minecraft_overlord_user: user to rule them all in the game (default == none)
* minecraft_upstart_respawn_limit: number of spawns and time to spawn (default == 3 120)
