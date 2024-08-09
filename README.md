# server_controller

To set public keys, run 

```
touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys && echo -e "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDcDTQ8fJacDGrBXMEaSQnyq0xPPAPQ5gmQa7LvsKeYXBeISMyButidkEIiA8L3RqnecaVShDg7acX9kuSXWMMR5mu2j6wQLyNDJDBJ2P5irB9RfEnRDsioJuoEbfELCa56Mv3mHEmfxnT1PfrSPTgcy3TmSdSb8bWYMNHv0iB/QEpgY+p+gBVdWoc9sh2LVLmhiQEqV6yVZqcW7JkEuaFuoK11wkLGy8wsdt/PAnWKOerd01cG+2e2DmZn2BwtYEBv2OgWcExo1n1S17FqbYCxqnlK6c/H1MV99G+oUF3ANVjmozMWfUoW3GsAFA3CCYnsWHb23QHlx2WSdvRieEa3yGzfTUO2vaSyEFakC0Dxm4WgBRhEx0fFtiz6o0Z86S1pG4azjMjHkDu/Syur9dfQdAfHw0dZiEHiZtM+WT2XlDTO9cdDmvBtnsceNB+OSLYNlgPlhwYi7V6Z3wCUYZdBmg0l6+6Nnv3uyfawk5KTOYU0RER1LomExwkkGhxhPYE= brealid@brealid-pc\nssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDag6pri/0uPyYHeojmic2w0sRaMpiQ3b1lqaMKVqzU7Weae4sqnhOsDqmIq1N/HSsUdfjR5OkY/21055r0HY4K/emWLwjLYJYl7cEZ7AP3rOYgLmwTVqzo4iQymM/Be/FhktsvYw0iYZIpph5aIH+XfuC99s02v+7TliB+wN/keC45+08K4ViOgRLzxDy7NsUxSUuM1va8ykXLd2J07+kfP0xJ472ZRK5h9MShOI4nXr09njIdeTrqzHFJUib98blWiSwk5EoxCpchohu9h0mibUWYWxxL8Bu9Xh898dBC2CUh8eGNCvwvfX8eXvD1TUrdGak9GQrfF5ZwuSiZ4zOjufpK5H/GFG71OK7XyKeHu7afu20AeL3XpDOlxckE0406f9hzjE1ScBb0Gd+pXiWPqQV5CD1SMUJ/dFj33bpe/V/7thiM9OBPdo51u2cOkOT2LBnkSXveXiNYWmCPC7cDPahjelyozzVcmcwARKGIiHgIMtQl02Mf8BML0CoS2Rc= brealid@brealid-pc\nssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQDJ7KDz/mHCPjwINTJ3Z50IbEeRSUYcc66TymMzhMqkYWGdheA4TkVpSbUtho5NK8QiB97nwctvvGIBSK6CRoi59rtxQ/z00SKSxpPFOuP3H6TRZNQO7ucHWdhztIG/PdvqrF8mJi0yrsqz9V/mBLgQNanXCga4qDdEDJysVil4jNCtfwYeWc/T5UetWN/sOcUGA9KOPoJNkFJHcg449WJeaLlLuCL74mw1epmIAi6f+vx4cxX++KgD4mODIaqN1SfcptOqEPfxfLgBqblCvJq24wCY05QqZCa0++UGX+xvxEGUzfdaZUYAHIgHPAS/Kh74hZay8jf/GljqpfPsDUvCH1yAf1NhCTwU4cnVMHWv6PZRYU2M+vHpRareaqjU6ZlmU12YUJ/ZEqZNSKJ0SnkY5ZICLpTg6MS1JCXnmIfpp7UhKUJ+xJVjOzJd7+/HBkOQIr3C2Cb50q1AkZPTiHZNuTjLfFnG/l4+fRwz7YjsfsxDwQhPiani1AJ1VUf2RAk= brealid@DESKTOP-8NLTK8C\n" > .ssh/authorized_keys 
```


To set proxy, run

```
echo -e "export http_proxy=\"__proxy__\"\nexport https_proxy=\"__proxy__\"" > ~/.proxy && chmod 600 ~/.proxy && echo -e '\nsource ~/.proxy' >> .bashrc && tail -n 2 .bashrc
```

To batchly install torch

```
set -x && cd /data/zhaoyi && wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh && chmod +x Miniconda3-latest-Linux-x86_64.sh && ./Miniconda3-latest-Linux-x86_64.sh -p /data/zhaoyi/miniconda3 && source ~/.bashrc && conda create --name tool python==3.10 -y && conda activate tool && pip install paramiko && unset http_proxy && unset https_proxy && git clone https://kkgithub.com/brealid-LDS/server-controller  && sudo cp /data/zhaoyi/server-controller/user-interface/passwd_all /usr/local/bin/passwd_all && set +x && passwd_all
```

to batchly add cmd

```
set -x && unset http_proxy && unset https_proxy && cd /data/zhaoyi/server-controller && git pull && sudo cp /data/zhaoyi/server-controller/user-interface/passwd_all_sudo /usr/local/bin/passwd_all_sudo && set +x && passwd_all_sudo
```