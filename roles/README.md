Create roles here, in either the Role Ruby DSL (.rb) or JSON (.json) files. To
install roles on the server, use knife.

For example, create `roles/base_example.rb`:

    name "base_example" description "Example base role applied to all nodes." #
    List of recipes and roles to apply. Requires Chef 0.8, earlier versions use
    'recipes()'. #run_list() # Attributes applied if the node doesn't have it
    set already. #default_attributes() # Attributes applied no matter what the
    node has set already. #override_attributes()

Then upload it to the Chef Server:

    knife role from file roles/base_example.rb

## vagrant role

Install mongo and rvm, other configuration inside each Vagrantfile project
related

~~~json
{
    "name": "vagrant",
    "description": "Setup vagrant environment",
    "json_class": "Chef::Role",
    "default_attributes": {},
    "override_attributes": {},
    "chef_type": "role",
    "run_list": ["recipe[mongodb]", "recipe[rvm::vagrant]", "recipe[rvm::user]"],
    "env_run_lists": {}
}
~~~