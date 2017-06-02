---
title: "Интеграция SQL Server со средой CLR | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Интеграция SQL Server со средой CLR
В версии SQL Server 2005 появилась поддержка интеграции сервера со средой CLR инфраструктуры .NET Framework для Microsoft Windows.  Это означает, что хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции, определяемые пользователем агрегатные функции и возвращающие табличные значение потоковые функции теперь можно разрабатывать с использованием любого языка .NET Framework, включая Microsoft Visual Basic .NET и Microsoft Visual C\#.  Пространство имен <xref:Microsoft.SqlServer.Server> содержит ряд новых API\-интерфейсов, что позволяет обеспечить взаимодействие управляемого кода со средой Microsoft SQL Server.  
  
 В настоящем разделе приведено описание средств и особенностей функционирования, которые появляются в результате интеграции SQL Server со средой CLR, а также внутрипроцессные модули SQL Server, предназначенные для поддержки технологии ADO.NET.  
  
 Этот раздел предназначен для предоставления лишь такого количества сведений, с которого можно приступать к программированию в рамках интеграции SQL Server со средой CLR, и не рассчитан на всестороннее изложение.  Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Основные понятия программирования при интеграции со средой CLR](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## В этом подразделе  
 [Введение в интеграцию SQL Server со средой CLR](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Предоставляет вводные сведения об интеграции SQL Server со средой CLR.  Приводятся ссылки на дополнительные разделы.  
  
 [Определяемые пользователем функции среды CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Содержит описание реализации и использования различных типов функций среды CLR: возвращающих табличное значение, скалярных и определяемых пользователем агрегатных функций.  
  
 [Определяемые пользователем типы данных CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Показывает, как реализовать и использовать определяемые пользователем типы среды CLR.  Приводятся ссылки на дополнительные разделы.  
  
 [Хранимые процедуры CLR](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Показывает, как реализовать и использовать хранимые процедуры среды CLR.  Приводятся ссылки на дополнительные разделы.  
  
 [Триггеры CLR](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Показывает, как реализовать и использовать триггеры CLR.  Приводятся ссылки на дополнительные разделы.  
  
 [Контекстное соединение](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Описывает контекстное соединение.  
  
 [Особое поведение ADO.NET в процессе SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Описывает внутрипроцессные модули SQL Server, предназначенные для поддержки технологии ADO.NET, и контекстное соединение.  Приводятся ссылки на дополнительные разделы.  
  
## См. также  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)   
 [Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ru-ru/5358a825-e19b-49aa-8214-674ce5fed1da)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)