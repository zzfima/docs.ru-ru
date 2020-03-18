---
ms.openlocfilehash: 566a3e0455b30e901b09be88b4256ffe67bdc2b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802527"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a>Функция сохраняемости SQL для рабочего процесса добавляет кластеры первичных ключей и не допускает значения NULL в некоторых столбцах

|   |   |
|---|---|
|Подробнее|Начиная с версии .NET Framework 4.7, таблицы, созданные для хранилища экземпляров рабочего процесса SQL (SWIS) с помощью скрипта SqlWorkflowInstanceStoreSchema.sql, используют кластеризованные первичные ключи. Из-за этого удостоверения не поддерживают значения <code>null</code>. Это изменение не влияет на работу SWIS. Были внесены обновления в поддержку механизма репликации транзакций SQL Server.|
|Предложение|Чтобы реализовать это изменение, в существующую установку необходимо добавить SQL-файл SqlWorkflowInstanceStoreSchemaUpgrade.sql. В новых установках баз данных это изменение реализуется автоматически.|
|Область|Пограничный случай|
|Version|4.7|
|Type|Параметры выполнения|
