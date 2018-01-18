---
title: "Безопасность интеграции CLR в SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4364e35bbce3261c8f6e6c45002d5a603007b85
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="clr-integration-security-in-sql-server"></a>Безопасность интеграции CLR в SQL Server
Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework. Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C#.  
  
 Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода (CAS). В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных. SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.  
  
## <a name="external-resources"></a>Внешние ресурсы  
 Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.  
  
|Ресурс|Описание:|  
|--------------|-----------------|  
|[Управление доступом для кода](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|Содержит подразделы, описывающие средства CAS на платформе .NET Framework.|  
|[Безопасность интеграции со средой CLR](http://go.microsoft.com/fwlink/?LinkId=59998)|Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.|  
  
## <a name="see-also"></a>См. также  
 [Защита приложений ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Сценарии безопасности приложений в SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Интеграция среды CLR и SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
