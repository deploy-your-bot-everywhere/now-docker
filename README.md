# now-docker

1. Регистрируемся на сайте [now.sh](https://zeit.co/now)
2. Скачиваем [now-cli](https://zeit.co/download#now-cli)
3. Клонируем репозиторий
```bash
╰─ git clone https://github.com/deploy-your-bot-everywhere/now-docker.git
cd now-docker
```
4. Логинимся через now-cli и подтверждаем email
```bash
╰─ now login
> We sent an email to example@gmail.com. Please follow the steps provided
  inside it and make sure the security code matches Eager Black Rhinoceros.
✔ Email confirmed
✔ Fetched your personal details
> Ready! Authentication token and personal details saved in "~/.now"
```
5. Деплоим
> Передаем токен и порт через [переменные окружения](https://zeit.co/docs/getting-started/environment-variables)
```bash
╰─ now -e TOKEN=123405366:AAEgfyGc3kfUjqj5dK7h08vFpGNU36p-APA -e PORT=3000
> Deploying ~/Projects/deploy-your-bot-everywhere/now-docker under example@gmail.com
> Synced 1 file (45B) [1s]
> https://now-docker-tcjxrydgoz.now.sh [in clipboard] (bru1) [10s]
> Building…
> Sending build context to Docker daemon  6.656kB
> Step 1/9 : FROM python:3.7-alpine
>  ---> 408808fb1a9e
> Step 2/9 : ENV TOKEN $TOKEN
>  ---> Using cache
>  ---> 75c2f7777be8
> Step 3/9 : ENV NOW_URL $NOW_URL
>  ---> Using cache
>  ---> b8b9312b451b
> Step 4/9 : ENV PORT $PORT
>  ---> Running in c2c6978145f9
>  ---> 16592be4dbe9
> Removing intermediate container c2c6978145f9
> Step 5/9 : ADD ./requirements.txt /tmp/requirements.txt
>  ---> 5b3681156d5a
> Step 6/9 : RUN pip install -r /tmp/requirements.txt
>  ---> Running in 8958ac9dbb60
> Collecting aiogram (from -r /tmp/requirements.txt (line 1))
>   Downloading https://files.pythonhosted.org/packages/59/f0/a6212f62fce3da9a530ad4dd25e5c049627fc10107b99a53a874a90009c5/aiogram-2.0-py3-none-any.whl (130kB)
> Collecting aiohttp (from -r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/70/27/6098b4b60a3302a97f8ec97eb85d42f55a2fa904da4a369235a8e3b84352/aiohttp-3.4.4.tar.gz (822kB)
>   Installing build dependencies: started
>   Installing build dependencies: finished with status 'done'
> Collecting Babel>=2.6.0 (from aiogram->-r /tmp/requirements.txt (line 1))
>   Downloading https://files.pythonhosted.org/packages/b8/ad/c6f60602d3ee3d92fbed87675b6fb6a6f9a38c223343ababdb44ba201f10/Babel-2.6.0-py2.py3-none-any.whl (8.1MB)
> Collecting certifi>=2018.8.24 (from aiogram->-r /tmp/requirements.txt (line 1))
>   Downloading https://files.pythonhosted.org/packages/56/9d/1d02dd80bc4cd955f98980f28c5ee2200e1209292d5f9e9cc8d030d18655/certifi-2018.10.15-py2.py3-none-any.whl (146kB)
> Collecting attrs>=17.3.0 (from aiohttp->-r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/3a/e1/5f9023cc983f1a628a8c2fd051ad19e76ff7b142a0faf329336f9a62a514/attrs-18.2.0-py2.py3-none-any.whl
> Collecting chardet<4.0,>=2.0 (from aiohttp->-r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/bc/a9/01ffebfb562e4274b6487b4bb1ddec7ca55ec7510b22e4c51f14098443b8/chardet-3.0.4-py2.py3-none-any.whl (133kB)
> Collecting multidict<5.0,>=4.0 (from aiohttp->-r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/b3/5f/5c29cde8511c95fad045b9ecaf2e76f0da18761e8363a82594f5a58c2ced/multidict-4.4.2.tar.gz (118kB)
> Collecting async_timeout<4.0,>=3.0 (from aiohttp->-r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/e1/1e/5a4441be21b0726c4464f3f23c8b19628372f606755a9d2e46c187e65ec4/async_timeout-3.0.1-py3-none-any.whl
> Collecting yarl<2.0,>=1.0 (from aiohttp->-r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/43/b8/057c3e5b546ff4b24263164ecda13f6962d85c9dc477fcc0bcdcb3adb658/yarl-1.2.6.tar.gz (159kB)
> Collecting pytz>=0a (from Babel>=2.6.0->aiogram->-r /tmp/requirements.txt (line 1))
>   Downloading https://files.pythonhosted.org/packages/f8/0e/2365ddc010afb3d79147f1dd544e5ee24bf4ece58ab99b16fbb465ce6dc0/pytz-2018.7-py2.py3-none-any.whl (506kB)
> Collecting idna>=2.0 (from yarl<2.0,>=1.0->aiohttp->-r /tmp/requirements.txt (line 2))
>   Downloading https://files.pythonhosted.org/packages/4b/2a/0276479a4b3caeb8a8c1af2f8e4355746a97fab05a372e4a2c6a6b876165/idna-2.7-py2.py3-none-any.whl (58kB)
> Building wheels for collected packages: aiohttp, multidict, yarl
>   Running setup.py bdist_wheel for aiohttp: started
>   Running setup.py bdist_wheel for aiohttp: finished with status 'done'
>   Stored in directory: /root/.cache/pip/wheels/2a/96/52/eb6dabe121252879286b5cc0a3164e2b263dc74b5bc09255b8
>   Running setup.py bdist_wheel for multidict: started
>   Running setup.py bdist_wheel for multidict: finished with status 'done'
>   Stored in directory: /root/.cache/pip/wheels/a2/9b/29/c1bde5ef4d1cd58bb0621113fb4929028ab9326e1dbf38bca6
>   Running setup.py bdist_wheel for yarl: started
>   Running setup.py bdist_wheel for yarl: finished with status 'done'
>   Stored in directory: /root/.cache/pip/wheels/fd/1c/e7/9df9bfc03a2f55c2201b52db3545b1314eb807148563a6521b
> Successfully built aiohttp multidict yarl
> Installing collected packages: pytz, Babel, attrs, chardet, multidict, async-timeout, idna, yarl, aiohttp, certifi, aiogram
> Successfully installed Babel-2.6.0 aiogram-2.0 aiohttp-3.4.4 async-timeout-3.0.1 attrs-18.2.0 certifi-2018.10.15 chardet-3.0.4 idna-2.7 multidict-4.4.2 pytz-2018.7 yarl-1.2.6
>  ---> 21e85444849b
> Removing intermediate container 8958ac9dbb60
> Step 7/9 : ADD ./main.py /opt/main.py
>  ---> aa30916ff40d
> Step 8/9 : WORKDIR /opt
>  ---> ec633a7c8050
> Removing intermediate container f144c21436c3
> Step 9/9 : CMD python main.py
>  ---> Running in 52a2b846fe46
>  ---> cfd65dcdfc6c
> Removing intermediate container 52a2b846fe46
> Successfully built cfd65dcdfc6c
> Successfully tagged build:sY6kELJPuaLJw1YwPTPxJxcM_1541616553
> ▲ Assembling image
> ▲ Storing image (57.3M)
> Build completed
> Verifying instantiation in bru1
> [0] INFO:aiogram:Bot: Deploying Now [@deploying_now_bot]
> ✔ Scaled 1 instance in bru1 [17s]
> Success! Deployment ready
```
6. Смотрим запущенные приложения
```bash
╰─ now ls 
> 1 total deployment found under example@gmail.com [517ms]
> To list more deployments for an app run `now ls [app]`

  app           url                             inst #    type      state    age
  now-docker    now-docker-tcjxrydgoz.now.sh         -    DOCKER    READY    11m
```
7. Логи можно посмотреть `now logs <url>`
