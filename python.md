# Setting Up Python

## Add Python to asdf
Asdf commands to add python:
```
asdf plugin add python
asdf install python latest
asdf local python latest
```


## Using Virtualenv 
Installing:
```
pip install virtualenv
virtualenv venv
```
Manually activate/deactivate virtualenv:
```
source venv/bin/activate
deactivate
```

## Using Direnv
To auto-activate virtualenv.
`echo 'eval "$(direnv hook zsh)"' >> ~/.zshrc`
It needs the .envrc in the project directory
`echo "export VIRTUAL_ENV=$PWD/venv\nexport PATH=$PWD/venv/bin:\$PATH" > .envrc`
`direnv allow`


## Verifying 
Do a `which python` and `which pip` to confirm it’s pointing to the right ones, i.e. the ones inside the venv.
