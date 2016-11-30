# Docker-PuppetLabs-
PuppetLabs server

#create a Docker network
docker network create vlan

#start the Puppet Server with your own Puppet code, you can mount your own directory at /etc/puppetlabs/code.

docker run --net vlan --name puppet --hostname puppet -v /code:/etc/puppetlabs/code/ puppet/puppetserver-standalone

# run a simple agent.

docker run --net vlan puppet/puppet-agent-alpine

