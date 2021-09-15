# litelitelite_infra
litelitelite Infra repository

Решение основного и дополнительного задания по bastion

Необходимо изменить конфиг ssh в такой вид:
Host bastion
  Hostname <внешний IP бастиона>
  User appuser
  IdentityFile /root/.ssh/appuser
  ControlPath ~/.ssh/cm-%r@%h:%p
  ControlMaster auto
  ControlPersist 1m
Host someinternalhost
  Hostname <внутренний IP>
  User appuser
  ProxyCommand ssh -W %h:%p bastion
  IdentityFile /root/.ssh/appuser

bastion_IP = 62.84.115.157
someinternalhost_IP = 10.128.0.15
