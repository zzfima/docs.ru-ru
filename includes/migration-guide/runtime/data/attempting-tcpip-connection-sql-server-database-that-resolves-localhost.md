---
ms.openlocfilehash: 8ac6d50b192001f6d924b2ffe4a367a33fc2c689
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857600"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с `localhost`, завершается ошибкой

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6 и 4.6.1 попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с <code>localhost</code>, завершается ошибкой: &quot;При установлении подключения к SQL Server произошла ошибка сети или ошибка экземпляра. Сервер не найден или недоступен. Проверьте правильность имени экземпляра и настройку сервера SQL Server для удаленных подключений. (поставщик: сетевые интерфейсы SQL, ошибка: 26 — ошибка при обнаружении указанного сервера или экземпляра)&quot;|
|Предложение|Эта проблема устранена, и восстановлено прежнее поведение в .NET Framework 4.6.2. Для подключения к базе данных SQL Server, которой сопоставляется <code>localhost</code>, выполните обновление до .NET Framework 4.6.2.|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Среда выполнения|

