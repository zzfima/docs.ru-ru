---
ms.openlocfilehash: 33c262ebe131aade2b32d824395721f098640cf9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857599"
---
### <a name="connection-pool-blocking-period-for-azure-sql-databases-is-removed"></a>Период блокировки пула соединений для баз данных Azure SQL удален

|   |   |
|---|---|
|Подробнее|Начиная с .NET Framework 4.6.2 в запросах на открытие подключения к известным базам данных Azure SQL (*.database.windows.net, *.database.chinacloudapi.cn, *.database.usgovcloudapi.net, *.database.cloudapi.de) удален период блокировки пула соединения, и ошибки открытия подключения не кэшируются. Почти сразу же после временных ошибок подключения будут выполняться повторные попытки запросов на открытие подключения. Это изменение позволяет немедленно повторять попытку открытого подключения к базам данных Azure SQL, повышая тем самым производительность облачных приложений. Для всех остальных попыток подключений период блокировки пула подключений продолжает действовать и далее.<p/>В .NET Framework 4.6.1 и более ранних версий, когда приложение обнаруживает временный сбой соединения при подключении к базе данных, невозможно быстро повторять попытки подключения, так как пул подключений кэширует ошибку и повторно создает ее в периоде от 5 секунд до 1 минуты. Дополнительные сведения см. в разделе [Пулы подключений SQL Server (ADO.NET)](~/docs/framework/data/adonet/sql-server-connection-pooling.md). Такое поведение является проблемным для подключений к базам данных Azure SQL, так как они часто завершаются временными ошибками, которые обычно устраняются через несколько секунд. Функция блокировки пула соединений означает, что приложение не может подключиться к базе данных в течение продолжительного периода, даже если база данных доступна и приложению необходимо преобразование в течение нескольких секунд.|
|Предложение|Если такое поведение нежелательно, вы можете настроить период блокирования пула подключений, задав свойство <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod?displayProperty=name>, представленное в .NET Framework 4.6.2. Значение этого свойства является членом перечисления <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=name>, которое принимает одно из трех значений:<ul><li><xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock></li><li><xref:System.Data.SqlClient.PoolBlockingPeriod.Auto></li><li><xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock></li></ul>Чтобы восстановить прежнее поведение, задайте свойству <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod?displayProperty=name> значение <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock>.|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Data.Common.DbConnection.OpenAsync?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
