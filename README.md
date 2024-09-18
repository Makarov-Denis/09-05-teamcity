# Домашнее задание к занятию 11 «Teamcity» Макаров Денис

## Подготовка к выполнению

1. В Yandex Cloud создайте новый инстанс (4CPU4RAM) на основе образа `jetbrains/teamcity-server`.
2. Дождитесь запуска teamcity, выполните первоначальную настройку.
3. Создайте ещё один инстанс (2CPU4RAM) на основе образа `jetbrains/teamcity-agent`. Пропишите к нему переменную окружения `SERVER_URL: "http://<teamcity_url>:8111"`.
4. Авторизуйте агент.
5. Сделайте fork [репозитория](https://github.com/aragastmatb/example-teamcity).
6. Создайте VM (2CPU4RAM) и запустите [playbook](./infrastructure).

![oblako](https://github.com/user-attachments/assets/ed1552f3-3148-4d05-a690-ffd2886808e6)

## Основная часть

1. Создайте новый проект в teamcity на основе fork.
2. Сделайте autodetect конфигурации.
3. Сохраните необходимые шаги, запустите первую сборку master.

![teamcity1](https://github.com/user-attachments/assets/0b705680-fcec-4e3d-8ab9-676dd1688a92)

![teamcity2](https://github.com/user-attachments/assets/4f2ea4a4-c890-4278-999d-4e25003c145f)

![build1](https://github.com/user-attachments/assets/5939f41d-ebd2-4df1-a37d-18d3a15277a6)

4. Поменяйте условия сборки: если сборка по ветке `master`, то должен происходит `mvn clean deploy`, иначе `mvn clean test`.
5. Для deploy будет необходимо загрузить [settings.xml](./teamcity/settings.xml) в набор конфигураций maven у teamcity, предварительно записав туда креды для подключения к nexus.
6. В pom.xml необходимо поменять ссылки на репозиторий и nexus.
7. Запустите сборку по master, убедитесь, что всё прошло успешно и артефакт появился в nexus.

![nexus1](https://github.com/user-attachments/assets/f538a05d-064f-43bc-8c42-5adcc575eb34)


8. Мигрируйте `build configuration` в репозиторий.


Ссылка на [.teamsity]https://github.com/Makarov-Denis/example-teamcity.git

9. Создайте отдельную ветку `feature/add_reply` в репозитории.
10. Напишите новый метод для класса Welcomer: метод должен возвращать произвольную реплику, содержащую слово `hunter`.
11. Дополните тест для нового метода на поиск слова `hunter` в новой реплике.
12. Сделайте push всех изменений в новую ветку репозитория.
13. Убедитесь, что сборка самостоятельно запустилась, тесты прошли успешно.

![izm1](https://github.com/user-attachments/assets/3278fa0b-9040-44ce-af42-4ed3821edad3)

![izm2](https://github.com/user-attachments/assets/9ed71b6d-c695-4620-9f75-5c32c2dcfcd4)

![izm3](https://github.com/user-attachments/assets/6555cb07-353f-4f2d-a843-ceac3fac9d2d)

14. Внесите изменения из произвольной ветки `feature/add_reply` в `master` через `Merge`.

15. Убедитесь, что нет собранного артефакта в сборке по ветке `master`
16. Настройте конфигурацию так, чтобы она собирала `.jar` в артефакты сборки.
17. Проведите повторную сборку мастера, убедитесь, что сбора прошла успешно и артефакты собраны.

![izm5](https://github.com/user-attachments/assets/d9ec4cde-6796-4a0a-b339-0aa9c8e0fb73)

![git artifact](https://github.com/user-attachments/assets/0bbcaaa3-a0bc-45be-aa2e-a5abe46b7c73)

18. Проверьте, что конфигурация в репозитории содержит все настройки конфигурации из teamcity.

![git](https://github.com/user-attachments/assets/d4142594-420c-4eb3-9d2c-76adfdbd89f1)


19. В ответе пришлите ссылку на репозиторий.

[.teamsity](https://github.com/Makarov-Denis/example-teamcity.git)

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
