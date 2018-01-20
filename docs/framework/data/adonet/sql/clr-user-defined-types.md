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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ed299dd91b16815cbbb50cd51602bb0161ec6939
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="clr-user-defined-types"></a>Пользовательские типы CLR
Microsoft SQL Server предоставляет поддержку определяемых пользователем типов данных (UDT), реализованную при помощи среды CLR в Microsoft .NET Framework. Среда CLR встроена в SQL Server. Этот механизм позволяет расширять систему типов базы данных. Определяемые пользователем типы дают возможность расширять систему типов данных SQL Server, а также позволяют определять сложные структурированные типы.  
  
 Для архитектуры приложений использование определяемых пользователем типов имеет два основных преимущества.  
  
-   Строгая инкапсуляция (и на клиенте, и на сервере) между внутренним состоянием и внешней функциональностью.  
  
-   Тесная интеграция между другими связанными функциями сервера. После определения собственного типа данных его можно использовать во всех контекстах, где в SQL Server можно использовать системные типы, включая определения столбцов, а также в качестве переменных, параметров, результатов функций, курсоров, триггеров и репликации.  
  
 Более подробные сведения см. в электронной документации по SQL Server для используемой версии SQL Server.  
  
 **Электронная документация по SQL Server**  
  
1.  [Определяемые пользователем типы CLR](http://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="see-also"></a>См. также  
 [Создание объектов SQL Server 2005 в управляемом коде](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
