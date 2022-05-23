This repo is for learning AWS CodeArtifact. For more information, please see https://sanhe-dev-exp-share.readthedocs.io/search.html?q=aws+codeartifact+root&check_keywords=yes&area=default#

.. code-block:: bash

    # configure twine, you need to run this every 24 hours for authentication
    aws codeartifact login --tool twine --domain aws-data-lab-sanhe --domain-owner 669508176277 --repository sanhe-pypi

    # build distribution
    rm -r dist
    python setup.py sdist bdist_wheel --universal

    # upload to code artifacts
    # "codeartifact" is the profile name, don't change it!
    twine upload --repository codeartifact dist/*

    # configure pip, you need to run this every 24 hours for authentication
    aws codeartifact login --tool pip --domain aws-data-lab-sanhe --domain-owner 669508176277 --repository sanhe-pypi

    # install your private library from code artifacts
    pip3.8 install learn_aws_code_artifact
    pip3.8 uninstall learn_aws_code_artifact
