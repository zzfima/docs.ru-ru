---
ms.openlocfilehash: e36dac19beb6251debef100656670a6623344eea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68237845"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a>Попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с `localhost`, завершается ошибкой

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.6 и 4.6.1 попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с <code>localhost</code>, завершается ошибкой: &quot;При установлении подключения к SQL Server произошла ошибка сети или ошибка экземпляра. Сервер не найден или недоступен. Проверьте правильность имени экземпляра и настройку сервера SQL Server для удаленных подключений. (поставщик: сетевые интерфейсы SQL, ошибка: 26 — ошибка при обнаружении указанного сервера или экземпляра)&quot;|
|Предложение|Эта проблема устранена, и восстановлено прежнее поведение в .NET Framework 4.6.2. Для подключения к базе данных SQL Server, которой сопоставляется <code>localhost</code>, выполните обновление до .NET Framework 4.6.2.|
|Область|Дополнительный номер|
|Version|4.6|
|Type|Параметры выполнения|
