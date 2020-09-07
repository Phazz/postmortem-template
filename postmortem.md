```
Remove this tip from your postmortem
Mandatory: 
1. Add quantified Business Impact, how many stores, transactions, sales, revenue, ... are impacted by the incident.
2. Make sure to add logs, screenshot, link to ITSM tickets, link to other incidents to store all the knowledge for the next reader. You can do so in the timeline or add a section at the end.
3. Make sure to add link to Actions tracked in a tracker (e.g. JIRA) in the Actions table below.
```
# Postmortem Product Example

## Date (dd/mm/yyyy):
01/01/2020

## Author: 
Pierre Lemperiere (20013673)
 
### Status:
OPEN (OPEN || COMPLETE)

### Summary:
Не работала печать УПД на кассах, не печатались списки возврата на кассах+в гк.
Скорость решения напрямую зависит от IT специалистов в магазине
Есть магазины без ит специалиста, в таких магазинах печать не будет работать, пока не появится ит специалист.

### Impact:
Были вынуждены отпускать клиентов из магазина без УПД, дежурный директор в магазине принимал возврат без списков возврата.

### Root causes:
Несогласованное изменение скрипта подключающего принтер к кассе, через файл Printers.csv на FS сервере магазина.

### Trigger:
Применение новой политики после перезагрузки кассы

### Resolution:
В каждом магазине It специалист должен поменять записи в файле, и только после этого работа будет восстановлена.

### Detection:
Инциденты от пользователей магазинов, звонки на л2.

### Duration: 
X days Y hours Z minutes
 
### Actions
| Actions | Type     | Owner | Ticket link |
|--------|----------|-------|-------------|
| Setup nightly test of printer accessibility from POS | prevent | pierre.lemperiere@adeo.com |             |
|        | mitigate |       |             |
| Automate notification to the team B when team A deploys in production       | process  |       |             |
| Freeze production until 02 Jan 2019 due to error budget exhaustion | other |       |             |



### Lessons Learned

### What went well:
Our monitoring notified us within 5 minutes of the incident as expected.

### What went wrong:
Team B was not aware of a chenge in the team A configuration. See action plan for continuous improvement action.

### Where we got lucky:
We say the issue before our customers as it occured at night and could fix before any customer noticed.

  
  
  
This template is inspired by Google,[^1].  
Find real world postmortem for inspiration from other teams in the industry at,[^2]

[^1]: https://landing.google.com/sre/sre-book/chapters/postmortem/
[^2]: https://github.com/danluu/post-mortems