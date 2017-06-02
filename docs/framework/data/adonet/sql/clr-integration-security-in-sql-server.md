---
title: "Безопасность интеграции со средой CLR в SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Безопасность интеграции со средой CLR в SQL Server
Microsoft SQL Server обеспечивает интеграцию компонентов среды CLR платформы .NET Framework.  Интеграция со средой CLR позволяет записывать хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции и потоковые возвращающие табличное значение функции, используя любой язык NET Framework, например Microsoft Visual Basic .NET или Microsoft Visual C\#.  
  
 Среда CLR поддерживает модель безопасности, называемую управлением доступом для кода \(CAS\).  В этой модели разрешения предоставляются сборкам на основе свидетельства, поставляемого кодом в метаданных.  SQL Server интегрирует пользовательскую модель безопасности SQL Server с кодом модели безопасности на основе доступа среды CLR.  
  
## Внешние ресурсы  
 Дополнительные сведения об интеграции со средой CLR в SQL Server см. в следующих ресурсах.  
  
|Ресурс|Описание|  
|------------|--------------|  
|[Code Access Security](http://msdn.microsoft.com/ru-ru/23a20143-241d-4fe5-9d9f-3933fd594c03)|Содержит подразделы, описывающие средства CAS на платформе .NET Framework.|  
|[Безопасность интеграции CLR](http://go.microsoft.com/fwlink/?LinkId=59998)|Содержит обсуждение модели безопасности для управляемого кода, выполняемого внутри SQL Server.|  
  
## См. также  
 [Защита приложений ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Сценарии защиты приложений в SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)   
 [Интеграция SQL Server со средой CLR](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)