aws codeartifact login --tool pip --domain aws-data-lab-sanhe --domain-owner 669508176277 --repository sanhe-pypi
aws codeartifact login --tool twine --domain aws-data-lab-sanhe --domain-owner 669508176277 --repository sanhe-pypi

twine upload dist/*
twine upload --repository codeartifact dist/*

learn_aws_code_artifact-0.0.1.tar.gz
learn_aws_code_artifact-0.0.1-py2.py3-none-any.whl

cd ~/Document/GitHub
pip3.8 install learn_aws_code_artifact
pip3.8 uninstall learn_aws_code_artifact
