---
ms.openlocfilehash: fcaee245e98dfe71beb4042a2664a14b64cf2398
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804923"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection больше не может подключаться к SQL Server 1997 или базам данных с помощью адаптера VIA

|   |   |
|---|---|
|Подробные сведения|Подключения к базам данных SQL Server с помощью [протокола Virtual Interface Adapter (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229%28v=sql.105%29) больше не поддерживаются. Протокол, используемый для подключения к базе данных SQL Server, отображается в строке подключения. Для соединения VIA указано via:&lt;имя_сервера&gt;. Если это приложение подключается к SQL через протокол, отличный от VIA (например, tcp: или np:), критических изменений не будет. Также больше не поддерживаются подключения к SQL Server 7 (1997).|
|Предложение|Не рекомендуется использовать протокол VIA. Выберите другой протокол для подключения к базам данных SQL. Обычно используется протокол TCP/IP. Дополнительные сведения см. в статье [Практическое руководство. Включение протокола TCP/IP для экземпляра базы данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Если доступ к базе данных осуществляется только из интрасети, протокол общих каналов может обеспечить более высокую производительность, если сеть работает слишком медленно.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)?displayProperty=nameWithType></li></ul>|
