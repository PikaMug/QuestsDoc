# Съхранение

Можете да изберете да промените опцията си за съхранение чрез настройката `storage-method` от [Конфигурационен файл на Quests](https://pikamug.gitbook.io/quests/setup/configuration#config.yml). Наличните възможности за избор са описани по-долу. Ако искате да промените метода си на съхранение по-късно, без да губите данни, първо използвайте [QuestsConverter](https://github.com/PikaMug/QuestsConverter).

### YAML

Това е изборът по подразбиране, който ще запази данните на играчите в отделни .yml файлове в папката _/Quests/data_. Препоръчва се за начинаещи и случайни потребители, тъй като работи веднага, без да се изисква допълнителна настройка.

### MySQL

Това тип ще запази данните на играчите в локална или отдалечена MySQL база данни, която сте конфигурирали преди това. Настройките за таблицата и влизане могат да бъдат зададени чрез настройката 'storage-data'. Пример за такава конфигурация може да изглежда така:

```
storage-data:
  address: localhost
  database: minecraft
  username: root
  password: myComplexPassword
  table_prefix: quests_
  pool-settings:
    max-pool-size: 10
    min-idle: 10
    max-lifetime: 1800000
    connection-timeout: 5000
```

Обърнете внимание, че HikariCP е засенчен вътрешно, за да се увеличи максимално скоростта на връзката на широко населени сървъри.

### Персонализиран

Разработчик може да избере да използва персонализирана опция за съхранение. Вижте [тук](https://github.com/PikaMug/Quests/tree/main/api/src/main/java/me/pikamug/quests/storage/implementation/custom).
