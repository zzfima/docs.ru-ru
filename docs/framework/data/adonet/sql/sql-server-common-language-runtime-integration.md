---
title: Интеграция среды CLR и SQL Server
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 5f6c1dcccaddeadb65e6fc949960b0232d00ed81
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43869095"
---
# <a name="sql-server-common-language-runtime-integration"></a>Интеграция среды CLR и SQL Server
В версии SQL Server 2005 появилась поддержка интеграции сервера со средой CLR инфраструктуры .NET Framework для Microsoft Windows. Это означает, что хранимые процедуры, триггеры, определяемые пользователем типы, определяемые пользователем функции, определяемые пользователем агрегатные функции и возвращающие табличные значение потоковые функции теперь можно разрабатывать с использованием любого языка .NET Framework, включая Microsoft Visual Basic .NET и Microsoft Visual C#. Пространство имен <xref:Microsoft.SqlServer.Server> содержит ряд новых API-интерфейсов, что позволяет обеспечить взаимодействие управляемого кода со средой Microsoft SQL Server.  
  
 В настоящем разделе приведено описание средств и особенностей функционирования, которые появляются в результате интеграции SQL Server со средой CLR, а также внутрипроцессные модули SQL Server, предназначенные для поддержки технологии ADO.NET.  
  
 Этот раздел предназначен для предоставления лишь такого количества сведений, с которого можно приступать к программированию в рамках интеграции SQL Server со средой CLR, и не рассчитан на всестороннее изложение. Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Распространенные языка среды CLR Integration основные понятия программирования](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a>В этом разделе  
 [Знакомство с интеграцией CLR в SQL Server](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 Предоставляет вводные сведения об интеграции SQL Server со средой CLR. Приводятся ссылки на дополнительные разделы.  
  
 [Определяемые пользователем функции среды CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 Содержит описание реализации и использования различных типов функций среды CLR: возвращающих табличное значение, скалярных и определяемых пользователем агрегатных функций.  
  
 [Определяемые пользователем типы CLR](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 Показывает, как реализовать и использовать определяемые пользователем типы среды CLR. Приводятся ссылки на дополнительные разделы.  
  
 [Хранимые процедуры CLR](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 Показывает, как реализовать и использовать хранимые процедуры среды CLR. Приводятся ссылки на дополнительные разделы.  
  
 [Триггеры CLR](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 Показывает, как реализовать и использовать триггеры CLR. Приводятся ссылки на дополнительные разделы.  
  
 [Подключение контекста](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 Описывает контекстное соединение.  
  
 [Внутрипроцессное поведение ADO.NET в SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 Описывает внутрипроцессные модули SQL Server, предназначенные для поддержки технологии ADO.NET, и контекстное соединение. Приводятся ссылки на дополнительные разделы.  
  
## <a name="see-also"></a>См. также  
 [SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [Создание объектов SQL Server 2005 в управляемом коде](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
