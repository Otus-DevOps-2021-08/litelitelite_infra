# litelitelite_infra
litelitelite Infra repository

## Выполнено ДЗ №5

- Установлен Packer
- Подготовлен образ ВМ с установленными MongoDB, Ruby
- Пробный запуск образа в YC
- Выполнена параметризация шаблона packer

## Запуск сборки образа

packer build -var-file=variables.json ./ubuntu16.json
