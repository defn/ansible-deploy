# install virtualenv
    sudo easy_install pip
    sudo pip install virtualenv

# install ansible in the virtualenv
    mkdir -p vendor/virtualenv
    virtualenv vendor/virtualenv
    source vendor/virtualenv/bin/activate
    pip install ansible

# using `defn/deploy`
    deploy -i inventory/localhost -e project_root="${HOME}/apps/ansible-deploy" deploy.yml
