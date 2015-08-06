# install virtualenv
    sudo easy_install pip
    sudo pip install virtualenv

# install ansible in the virtualenv
    mkdir -p vendor/virtualenv
    virtualenv vendor/virtualenv
    source vendor/virtualenv/bin/activate
    pip install ansible

# deploy ansible-deploy project to localhost into example/deployed
    cd example
    env ANSIBLE_SSH_ARGS="-o ForwardAgent=yes" ansible-playbook -i inventory/localhost -e project_root="$(pwd)/deployed" -e project_git_repo=$(git config --local remote.origin.url) site.yml

# using `defn/deploy`
    cd example
    deploy -i inventory/localhost -e project_root=$(pwd)/deployed site.yml
