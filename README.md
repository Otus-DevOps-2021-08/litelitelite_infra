# litelitelite_infra
litelitelite Infra repository

### Дополнительное задание №1:
>Предложить вариант решения для подключения из консоли при помощи команды вида ssh someinternalhost из локальной консоли рабочего устройства, чтобы подключение выполнялось по алиасу someinternalhost и внести его в README.md в вашем репозитории
- Добавлен config:

```
Host bastion
  Hostname 193.32.218.51
  User appuser
  IdentityFile /root/.ssh/appuser
  ControlPath ~/.ssh/cm-%r@%h:%p
  ControlMaster auto
  ControlPersist 1m

Host someinternalhost
  Hostname 10.128.0.15
  User appuser
  ProxyCommand ssh -W %h:%p bastion
  IdentityFile /root/.ssh/appuser
```

- Команда для подключения к хосту за бастионом через alias:

```
ssh someinternalhost
```
bastion_IP = 193.32.218.51
someinternalhost_IP = 10.128.0.15
