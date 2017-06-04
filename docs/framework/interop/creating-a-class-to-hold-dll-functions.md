---
title: "Creating a Class to Hold DLL Functions | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM interop, DLL functions"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "interoperation with unmanaged code, DLL functions"
  - "interoperation with unmanaged code, platform invoke"
  - "platform invoke, creating class for functions"
  - "DLL functions"
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Creating a Class to Hold DLL Functions
Заключение часто используемой функции DLL в оболочку управляемого класса представляет собой эффективный способ инкапсуляции функциональных возможностей платформы.  Хотя применение оболочки класса необязательно, оно удобно, так как процесс определения функций DLL может быть громоздким и представлять собой источник ошибок.  При программировании на Visual Basic или C\# функции DLL должны объявляться в пределах класса или модуля Visual Basic.  
  
 В классе для каждой вызываемой функции DLL должен быть определен статический метод.  Определение может включать дополнительные сведения, например, кодировку или соглашение о вызовах, используемое при передаче аргументов метода. Если эти сведения отсутствуют, используются параметры по умолчанию.  Полный список параметров объявлений и их значения по умолчанию см. в разделе [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
 После упаковки в оболочку методы для функции можно вызывать точно так же, как и методы для любой другой статической функции.  Вызов неуправляемого кода обрабатывает базовую экспортируемую функцию автоматически.  
  
 При разработке управляемого класса для вызова неуправляемого кода следует учитывать связи между классами и функциями DLL.  В частности, можно выполнить следующие действия.  
  
-   Объявлять функции DLL в существующем классе.  
  
-   Создавать для каждой функции DLL отдельный класс в целях изоляции и упрощения поиска функций.  
  
-   Создавать один класс для набора связанных функций DLL, формируя логические группирования и сокращая дополнительные издержки.  
  
 Разработчик может назвать класс и его методы по своему усмотрению.  Примеры, в которых показывается способ создания объявлений на основе .NET, предназначенных для использования с вызовом неуправляемого кода, см. в разделе [Маршалинг данных с вызовом неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## См. также  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [Identifying Functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)