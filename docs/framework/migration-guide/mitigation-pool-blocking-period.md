---
title: Устранение рисков. Период блокировки пула
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4c90a75ebbb9e4bc6248aadd709be8b5285ecd6
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409124"
---
# <a name="mitigation-pool-blocking-period"></a>Устранение рисков. Период блокировки пула
Период блокировки пула подключений был удален для подключений к базам данных Azure SQL.  
  
## <a name="additional-description"></a>Дополнительное описание  
 В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версиях, когда приложение обнаруживает временный сбой соединения при подключении к базе данных, невозможно быстро повторять попытки подключения, так как пул подключений кэширует ошибку и повторно создает ее в периоде от 5 секунд до 1 минуты. Дополнительные сведения см. в разделе [Пулы подключений SQL Server (ADO.NET)](../../../docs/framework/data/adonet/sql-server-connection-pooling.md). Такое поведение является проблемным для подключений к базам данных Azure SQL, так как они часто завершаются временными ошибками, которые обычно устраняются через несколько секунд. Функция блокировки пула соединений означает, что приложение не может подключиться к базе данных в течение продолжительного периода даже несмотря на доступность базы данных. Это вызывает особые сложности для веб-приложений, которые подключаются к базам данных Azure SQL и должны отображаться через несколько секунд.  
  
 Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], в открытых запросах подключения к известным базам данных Azure SQL (*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de) открытые ошибки подключения не кэшируются. Для всех остальных попыток подключений период блокировки пула подключений продолжает действовать и далее.  
  
## <a name="impact"></a>Последствия  
 Это изменение позволяет немедленно повторять попытку открытого подключения к базам данных Azure SQL, повышая тем самым производительность облачных приложений.  
  
## <a name="mitigation"></a>Устранение рисков  
 Для приложений, на которые это изменение оказывает существенное влияние, можно отдельно настроить интервал блокировки пула подключений, задав новое свойство <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType>.  Значение этого свойства является членом перечисления <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType>, которое принимает одно из трех значений:  
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
-   <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 Чтобы восстановить прежнее поведение, задайте свойству <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> значение <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также
- [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
