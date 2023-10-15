# Домашнее задание к занятию 1. «Введение в Ansible» - Пугач Евгений.


---

## `Подготовка к выполнению`

1. Установите Ansible версии 2.10 или выше.

```
root@pugach-agent1:~/08-ansible-01-base/playbook# ansible --version
ansible 2.10.8
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.9.2 (default, Feb 28 2021, 17:03:44) [GCC 10.2.1 20210110]
```

2. Создайте свой публичный репозиторий на GitHub с произвольным именем.

[>>Репозиторий](https://github.com/PugachEV72/08-ansible-01-base)

3. Скачайте Playbook из репозитория с домашним заданием и перенесите его в свой репозиторий.

[>>Playbook](https://github.com/PugachEV72/08-ansible-01-base/playbook)

---


## `Основная часть`

1. Попробуйте запустить playbook на окружении из test.yml, зафиксируйте значение, которое имеет факт some_fact  
для указанного хоста при выполнении playbook.

### Ответ:

Значение some_fact: `12`

![Скриншот 1](https://github.com/PugachEV72/Images/blob/master/2023-10-15_15-43-35.png)

---

2. Найдите файл с переменными (group_vars), в котором задаётся найденное в первом пункте значение, и поменяйте  
его на all default fact.

### Ответ:

![Скриншот 2](https://github.com/PugachEV72/Images/blob/master/2023-10-15_15-55-28.png)

---

3. Воспользуйтесь подготовленным (используется docker) или создайте собственное окружение для проведения  
дальнейших испытаний.

### Ответ:

![Скриншот 3](https://github.com/PugachEV72/Images/blob/master/2023-10-15_20-40-13.png)

---

4. Проведите запуск playbook на окружении из prod.yml. Зафиксируйте полученные значения some_fact для каждого из  
managed host.

### Ответ:

![Скриншот 4](https://github.com/PugachEV72/Images/blob/master/2023-10-15_20-50-20.png)

---

5. Добавьте факты в group_vars каждой из групп хостов так, чтобы для some_fact получились значения: для deb — deb  
default fact, для el — el default fact.
6. Повторите запуск playbook на окружении prod.yml. Убедитесь, что выдаются корректные значения для всех хостов.

### Ответ:

![Скриншот 5](https://github.com/PugachEV72/Images/blob/master/2023-10-15_16-08-20.png)

---

7. При помощи ansible-vault зашифруйте факты в group_vars/deb и group_vars/el с паролем netology.
8. Запустите playbook на окружении prod.yml. При запуске ansible должен запросить у вас пароль.  
Убедитесь в работоспособности.

### Ответ:

![Скриншот 6](https://github.com/PugachEV72/Images/blob/master/2023-10-15_17-59-29.png)

---

9. Посмотрите при помощи ansible-doc список плагинов для подключения. Выберите подходящий для работы на control node.

### Ответ:

![Скриншот 7](https://github.com/PugachEV72/Images/blob/master/2023-10-15_18-04-26.png)
![Скриншот 8](https://github.com/PugachEV72/Images/blob/master/2023-10-15_18-07-22.png)

---

10. В prod.yml добавьте новую группу хостов с именем local, в ней разместите localhost с необходимым типом подключения.

[>>Prod.yml](https://github.com/PugachEV72/08-ansible-01-base/blob/main/playbook/inventory/prod.yml)

---

11. Запустите playbook на окружении prod.yml. При запуске ansible должен запросить у вас пароль. Убедитесь, что факты  
some_fact для каждого из хостов определены из верных group_vars.

![Скриншот 9](https://github.com/PugachEV72/Images/blob/master/2023-10-15_21-16-38.png)

---

12. Заполните README.md ответами на вопросы. Сделайте git push в ветку master. В ответе отправьте ссылку на ваш открытый  
репозиторий с изменённым playbook и заполненным README.md.

[>>Репозиторий](https://github.com/PugachEV72/08-ansible-01-base)

---

## `Необязательная часть`

1. При помощи ansible-vault расшифруйте все зашифрованные файлы с переменными.
2. Зашифруйте отдельное значение PaSSw0rd для переменной some_fact паролем netology. Добавьте полученное значение  
в group_vars/all/exmp.yml.
3. Запустите playbook, убедитесь, что для нужных хостов применился новый fact.

### Ответ:

![Скриншот 10](https://github.com/PugachEV72/Images/blob/master/2023-10-15_19-02-17.png)
![Скриншот 11](https://github.com/PugachEV72/Images/blob/master/2023-10-15_19-03-37.png)

---

4. Добавьте новую группу хостов fedora, самостоятельно придумайте для неё переменную.

### Ответ:

![Скриншот 12](https://github.com/PugachEV72/Images/blob/master/2023-10-15_19-36-32.png)
![Скриншот 13](https://github.com/PugachEV72/Images/blob/master/2023-10-15_19-37-51.png)

---

