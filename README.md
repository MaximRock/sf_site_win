Правила именования веток.
=
---
Имена веток.
--
---
- Из ветки main создается ветка develop.

![Из ветки main создается ветка develop](https://wac-cdn.atlassian.com/dam/jcr:a13c18d6-94f3-4fc4-84fb-2b8f1b2fd339/01%20How%20it%20works.svg?cdnVersion=582)

---
- Из ветки develop создаются ветки feature.

![](https://wac-cdn.atlassian.com/dam/jcr:34c86360-8dea-4be4-92f7-6597d4d5bfae/02%20Feature%20branches.svg?cdnVersion=582)

---
- Из ветки develop создается ветка release.

![](https://wac-cdn.atlassian.com/dam/jcr:8f00f1a4-ef2d-498a-a2c6-8020bb97902f/03%20Release%20branches.svg?cdnVersion=582)

- Когда работа над веткой feature завершается, она сливается в ветку develop.
- Когда работа над веткой release завершается, она сливается с ветками develop и main.
---
- Если в ветке main обнаруживается проблема, из main создается ветка hotfix.

![](https://wac-cdn.atlassian.com/dam/jcr:cc0b526e-adb7-4d45-874e-9bcea9898b4a/04%20Hotfix%20branches.svg?cdnVersion=582)

- Когда работа над веткой hotfix завершается, она сливается с ветками develop и main.
---
Правила создания шаблона имени ветки.
--
---
- шаблон ветки feature:
    - {surname_name_< name feature >}
- шаблон ветки release:

    - X.Y.Z - где X, Y и Z — неотрицательные целые числа и НЕ ДОЛЖНЫ начинаться с нуля. X — мажорная версия, Y — минорная версия и Z — патч-версия. Каждый элемент ДОЛЖЕН увеличиваться численно. Например: 1.9.0 ->1.10.0 -> 1.11.0.

      {v 0.1.0}
- шаблон ветки hotfix:
  - {surname_name_< name bug >}

---

Процесс внесения своих изменений в основную кодовую базу.
--
---

- Каждый разработчик принимающий участие в проекте и имеющий доступ к репозиторию производит его клонирование на свой локальный репозиторий.
- Каждому разработчику присваивается своя ветка feature с указанием по шаблону имени ветки. Имя ветки может изменятся в зависимости от выполняемой задачи на проекте. 
- Разработчик заливает код в свою ветку, отправляет руководителю проекта Pull Request, для проверки и одобрения слияния с веткой develop.
- При выявлении бага в проекте в ветке main создается ветка hotfix с указанием имени по шаблону, разработчик перед слиянием кода в ветку hotfix отправляет Pull Request руководителю проекта и после проверки кода производит слияние с веткой main.
- Создание ветки release запускает следующий цикл релиза, и с этого момента новые функции добавить больше нельзя — допускается лишь исправление багов, создание документации и решение других задач, связанных с релизом. 

  Когда подготовка к поставке завершается, ветка release сливается с main и ей присваивается номер версии. Кроме того, нужно выполнить ее слияние с веткой develop, в которой с момента создания ветки релиза могли возникнуть изменения.

  Нумерацию release начинать с 0.1.0.
---
Инструкция для младших разработчиков по Git.
--
---
  - git checkout -b {surname_name_< branch pattern >} – создание и переход в ветку.
  - git branch – просмотр веток.
  - git branch – просмотр веток, также удаленных.
  - git merge develop – слияние с веткой develop.
  - git add . – добавить все изменения.
  - git commit -m «тест коммита» - коммит изменений.
  - git status - определение состояния файлов.
  - git log --graph - Отображает ASCII граф с ветвлениями и историей слияний.
  - git push – пушим на удаленный репозиторий.




