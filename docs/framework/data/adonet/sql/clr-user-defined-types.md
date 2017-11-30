---
title: "Пользовательские типы CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f70e0b0-3a0d-4eb1-b914-07a5d0c167c2
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e81cf54ed9dc516d88b8c7a97c8a5b33b8943d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="clr-user-defined-types"></a>Пользовательские типы CLR
Microsoft SQL Server предоставляет поддержку определяемых пользователем типов данных (UDT), реализованную при помощи среды CLR в Microsoft .NET Framework. Среда CLR встроена в SQL Server. Этот механизм позволяет расширять систему типов базы данных. Определяемые пользователем типы дают возможность расширять систему типов данных SQL Server, а также позволяют определять сложные структурированные типы.  
  
 Для архитектуры приложений использование определяемых пользователем типов имеет два основных преимущества.  
  
-   Строгая инкапсуляция (и на клиенте, и на сервере) между внутренним состоянием и внешней функциональностью.  
  
-   Тесная интеграция между другими связанными функциями сервера. После определения собственного типа данных его можно использовать во всех контекстах, где в SQL Server можно использовать системные типы, включая определения столбцов, а также в качестве переменных, параметров, результатов функций, курсоров, триггеров и репликации.  
  
 Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Определяемые пользователем типы среды CLR](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a>См. также  
 [Создание объектов SQL Server 2005 в управляемом коде](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
