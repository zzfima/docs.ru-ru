---
ms.openlocfilehash: cf1a8169351e29c18d85303fb32d4394877448f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235964"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a>Имя файла журнала, созданного методом ObjectContext.CreateDatabase, изменилось в соответствии со спецификациями SQL Server

|   |   |
|---|---|
|Подробные сведения|При вызове метода <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> либо напрямую, либо с использованием Code First с поставщиком SqlClient и значения AttachDBFilename в строке подключения он создает файл журнала с именем filename_log.ldf вместо filename.ldf (где filename — имя файла, заданное значением AttachDBFilename). Это изменение улучшает отладку, предоставляя файл журнала, имя которого соответствует спецификациям SQL Server.|
|Предложение|Если имя файла журнала важно для приложения, приложение следует обновить для использования стандартного формата имени файла _log.ldf.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
