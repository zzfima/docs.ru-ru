---
title: "Безопасность SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: c186b25aeaa42b7285316d7bc9de913dd7b89af7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2018
---
# <a name="sql-server-security"></a>Безопасность SQL Server
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] имеет множество функций, которые поддерживают создание безопасных приложений баз данных.  
  
 Такие общие угрозы безопасности, как кража данных или вандализм, существуют независимо от используемой версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Целостность данных также следует рассматривать как проблему безопасности. При отсутствии защиты данных они могут стать бесполезными, если разрешено нерегламентированное управление данными и в данные случайно или преднамеренно вносятся неверные значения или они полностью удаляются. Кроме того, зачастую существуют законодательные требования, которые необходимо соблюдать, например, касающиеся правильного хранения конфиденциальной информации. Хранение некоторых личных данных полностью запрещено в зависимости от законодательства, которое применяется в конкретной юрисдикции.  
  
 В каждой версии [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] есть свои средства безопасности, как и в каждой версии Windows, при этом возможности более поздних версий шире, чем возможности более ранних. Важно понимать, что сами по себе средства безопасности не могут гарантировать защиту приложения базы данных. Каждое приложение базы данных имеет уникальные требования, среду выполнения, модель развертывания, физическое расположение и количество пользователей. Некоторым приложениям, работающим локально, необходима минимальная защита, тогда как другим локальным приложениям или приложениям, развернутым через Интернет, могут требоваться строгие меры безопасности вместе с постоянным мониторингом и контролем.  
  
 Требования безопасности для приложения базы данных [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] следует рассматривать во время разработки, а не впоследствии. Оценка угроз еще на стадии разработки позволяет сократить потенциальный ущерб в случае обнаружения уязвимости.  
  
 Даже если первоначально приложение разработано безупречно, по мере развития системы могут появляться новые угрозы. Создание эшелонированной защиты вокруг базы данных позволяет свести к минимуму ущерб, причиняемый прорывом системы безопасности. На первой линии защиты необходимо сократить контактную зону для атаки злоумышленников. Для этого никогда не следует предоставлять больше прав доступа, чем необходимо.  
  
 В этом разделе кратко описываются средства безопасности в [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], которые нужны разработчикам. Здесь также приведены ссылки на соответствующие разделы электронной документации по [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] и другие ресурсы, где эти функции описаны более подробно.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Общие сведения о безопасности SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 Описание архитектуры и средств безопасности [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Сценарии безопасности приложений в SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 Подразделы с описанием различных сценариев обеспечения безопасности для приложений ADO.NET и [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].  
  
 [Безопасность SQL Server Express](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 Описание вопросов безопасности для [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express.  
  
## <a name="related-sections"></a>Связанные разделы  
[Центр обеспечения безопасности для ядра СУБД SQL Server и база данных Azure SQL](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
Вопросы безопасности для SQL Server и базы данных SQL Azure.

[Рекомендации по безопасности для установки SQL Server](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
Вопросы безопасности, которые следует учитывать перед установкой SQL Server.

## <a name="see-also"></a>См. также  
 [Защита приложений ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
