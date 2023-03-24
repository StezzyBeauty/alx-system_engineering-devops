# Configuration management

<img src=https://camo.githubusercontent.com/a8beca49d235c281f3d098778b0237c84c32a6d2a03fb1c583dcbc9fae119101/68747470733a2f2f7761632d63646e2e61746c61737369616e2e636f6d2f64616d2f6a63723a66343633353437382d343861312d343564312d396232662d3433643134623236363662612f436f6e66696775726174696f6e2d6d616e6167656d656e742d746f6f6c732d32782e706e673f63646e56657273696f6e3d363930>

Configuration management is a systems engineering process for establishing consistency of a product’s attributes throughout its life.

Puppet is a tool that helps you manage and automate the configuration of servers. When you use Puppet, you define the desired state of the systems in your infrastructure that you want to manage.

<img src=https://camo.githubusercontent.com/6bb1b866a761d8f689ca7187aaa0b7d171deba5a3cec723cec610536744f6ef3/68747470733a2f2f6d69726f2e6d656469756d2e636f6d2f6d61782f3732302f312a6a3052484e336f587a4f6658576c3758654c7a785a772e77656270>

Obviously writing Puppet code for your infrastructure requires an investment of time and energy, but in the long term, it is for sure a must-have.

## Project Requirements

- All your files will be interpreted on Ubuntu 20.04 LTS
- All your files should end with a new line
- A README.md file at the root of the folder of the project is mandatory
- Your Puppet manifests must pass puppet-lint version 2.1.1 without any errors
- Your Puppet manifests must run without error
- Your Puppet manifests first line must be a comment explaining what the Puppet manifest is about
- Your Puppet manifests files must end with the extension .pp

## Installing puppet and puppet-lint on ubuntu

### Commands on Terminal

```

$ apt-get update && upgrade -y

$ sudo apt-get install -y ruby=1:2.7+1 --allow-downgrades

$ sudo apt-get install -y ruby-augeas

$ sudo apt-get install -y ruby-shadow

$ sudo apt-get install -y puppet

#installs puppet linter
$ gem install puppet-lint

```
