---
title: "Одновременное выполнение в ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ade4a0531ae11b3707115956ef0218c0d1c3349c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="side-by-side-execution-in-adonet"></a>Одновременное выполнение в ADO.NET
Параллельное выполнение в платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] - это возможность выполнять приложение на компьютере, на котором установлено несколько версий [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], используя только ту версию, для которой приложение скомпилировано. Подробные сведения о настройке side-by-side выполнения см. в разделе [выполнения Side-by-Side](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Приложение, скомпилированное при помощи одной версии платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], может работать на другой версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Однако рекомендуется компилировать разные версии приложения для каждой установленной версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] и выполнять их по отдельности. В любом случае следует знать, какие изменения вносятся в разные версии [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], которые могут повлиять на прямую и обратную совместимость приложения.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Прямая и обратная совместимость  
 Прямая совместимость означает, что приложение может быть скомпилировано в более ранней версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], но по-прежнему будет работать в более поздней версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Код [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], написанный для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1, имеет прямую совместимость с более поздними версиями.  
  
 Обратная совместимость означает, что приложение, скомпилированное для более новой версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], будет работать и на предыдущих версиях [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] без потери функциональности. Разумеется, функции, появившиеся в новой версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], при этом будут недоступны.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Поставщик данных .NET Framework для ODBC  
 Начиная с версии 1.1, поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для ODBC (<xref:System.Data.Odbc>) является частью платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Поставщик данных ODBC доступен для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0, могут загрузить из [Центр разработчиков хранилищ и доступа к данным](http://go.microsoft.com/fwlink/?linkid=4173). Пространство имен для загруженного [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поставщика данных для ODBC **Microsoft.Data.Odbc**.  
  
 Если у вас есть приложение, разработанное для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0, использующий поставщик данных ODBC для подключения к источнику данных и вы хотите выполнить приложение [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1 или более поздней версии, необходимо обновить пространство имен для ODBC Поставщик данных для **System.Data.Odbc**. Затем приложение необходимо перекомпилировать для более поздней версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Если в приложении, разработанном для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 2.0 и более поздних версий, для подключения к источнику данных используется поставщик данных ODBC и это приложение необходимо запускать на платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0, то следует загрузить поставщик данных ODBC и установить его в систему [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0. Затем нужно возможность изменить пространство имен для поставщика данных ODBC на **Microsoft.Data.Odbc**и перекомпилировать приложение для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Поставщик данных .NET Framework для Oracle  
 Начиная с версии 1.1, поставщик данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для Oracle (<xref:System.Data.OracleClient>) является частью платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Поставщик данных доступен для [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0, могут загрузить из [Центр разработчиков хранилищ и доступа к данным](http://go.microsoft.com/fwlink/?linkid=4173).  
  
 Если в приложении, разработанном для платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 2.0 и более поздних версий, для подключения к источнику данных используется поставщик данных и это приложение необходимо запускать на платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0, то следует загрузить поставщик данных и установить его в систему [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0.  
  
## <a name="code-access-security"></a>Управление доступом для кода  
 Поставщики данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] в платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) должны выполняться с правами доступа FullTrust. Любая попытка использовать поставщики данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] из платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0 в зоне с правами доступа ниже FullTrust вызовет исключение <xref:System.Security.SecurityException>.  
  
 Однако, начиная с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 2.0, все поставщики данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] можно использовать в частично доверенных зонах. Кроме того, в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1 у поставщиков данных [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] появилась новая функция безопасности. Эта функция позволяет указывать, какие строки соединения могут использоваться в конкретной зоне безопасности. Также можно отключить использование пустых паролей для конкретной зоны безопасности. Для получения дополнительной информации см. [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Так как в каждой установке [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] есть отдельный файл Security.config, проблем с совместимостью параметров безопасности не возникает. Однако если в приложении используются дополнительные возможности безопасности платформы [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], появившиеся в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1 и более поздних версиях, то их невозможно будет распространить на систему версии 1.0.  
  
## <a name="sqlcommand-execution"></a>Выполнение SqlCommand  
 Начиная с [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1, процедура выполнения методом <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> команд в источнике данных изменилась.  
  
 В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> выполнял все команды в контексте **sp_executesql** хранимой процедуры. В результате этого команды, которые влияли на состояние соединения (например, SET NOCOUNT ON), применялись только к выполнению текущей команды. Состояние соединения не изменялось для любых последующих команд, выполнявшихся при открытом соединении.  
  
 В [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1 и более поздней версии, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> только выполняет команду в контексте **sp_executesql** хранимой процедуры, если команда содержит параметры, что позволяет повысить производительность. В результате этого, если команда, влияющая на состояние соединения, включена в непараметризованную команду, она изменяет состояние соединения для всех последующих команд, выполняемых при открытом соединении.  
  
 Рассмотрим следующий пакет команд, выполняемых при обращении к <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 На платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.1 и более поздних версий NOCOUNT останется в состоянии ON для всех последующих команд, выполняемых при открытом соединении. На платформе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] версии 1.0 NOCOUNT находится в состоянии ON только во время выполнения текущей команды.  
  
 Это изменение может влиять как на прямую, так и на обратную совместимость приложения, если оно зависит от поведения <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> для любой из версий платформы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Для приложений, которые работают и в более ранних, и более поздних версиях [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], можно написать собственный код, гарантирующий единообразное поведение независимо от используемой версии платформы. Если требуется сделать так, чтобы команда изменяла состояние соединения для всех последующих команд, рекомендуется выполнять команду с помощью <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Если требуется сделать так, чтобы команда не изменяла соединение для всех последующих команд, рекомендуется включать в нее команды для сброса состояния соединения. Пример:  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
