---
title: "SqlClient для Entity Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e2d95b1c63cf751a694051e5def09e20dd7ab7a9
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient для Entity Framework
В этом разделе описан поставщик данных .NET Framework для SQL Server (SqlClient), который позволяет платформе Entity Framework работать с сервером Microsoft SQL Server.  
  
## <a name="provider-schema-attribute"></a>Атрибут Provider элемента Schema  
 `Provider` является атрибутом элемента `Schema` в языке SSDL.  
  
 Для использования SqlClient нужно присвоить атрибуту `Provider` элемента `Schema` значение в виде строки «System.Data.SqlClient».  
  
## <a name="providermanifesttoken-schema-attribute"></a>Атрибут ProviderManifestToken элемента Schema  
 `ProviderManifestToken` - обязательный атрибут элемента `Schema` в SSDL. Этот маркер используется для загрузки манифеста поставщика при автономном использовании. Дополнительные сведения о `ProviderManifestToken` см. в разделе [элемент схемы (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).  
  
 SqlClient можно использовать в качестве поставщика данных для различных версий [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]. Эти версии имеют разные возможности. Например, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] не поддерживает типы `varchar(max)` и `nvarchar(max)`, представленные в [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].  
  
 SqlClient формирует и принимает следующие маркеры манифеста поставщика для различных версий SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  Начиная с [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, [ADO.NET Entity Data Model Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) не поддерживает SQL Server 2000.  
  
## <a name="provider-namespace-name"></a>Имя пространства имен поставщика  
 Все поставщики должны указывать пространство имен. Это свойство сообщает платформе Entity Framework о том, какой префикс используется поставщиком для конкретных конструкций, таких как типы или функции. Пространством имен для манифестов поставщика SqlClient является `SqlServer`. Дополнительные сведения о пространствах имен см. в разделе [пространства имен](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Типы  
 Поставщик SqlClient для платформы Entity Framework предоставляет сведения о сопоставлении между типами концептуальной модели и типами SQL Server. Дополнительные сведения см. в разделе [SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Функции  
 Поставщик SqlClient для платформы Entity Framework определяет список функций, поддерживаемых поставщиком. Список поддерживаемых функций см. в разделе [функции SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Функции SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [Типы SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Известные проблемы SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>См. также  
 [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [Справочник по языку](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [Известные проблемы в Поставщик SqlClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
