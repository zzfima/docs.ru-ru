---
title: "Создание класса, содержащего функции DLL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ed5ef9b7aaad3405ff31ff45ee8d0b22f56f51d7
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2018
---
# <a name="creating-a-class-to-hold-dll-functions"></a>Создание класса, содержащего функции DLL
Упаковка часто используемых функций DLL в управляемый класс позволяет эффективно инкапсулировать функциональные возможности платформы. Делать это в каждом случае необязательно, однако использование оболочки класса удобно, поскольку определение функций DLL может быть затруднительно и нередко приводит к ошибкам. При программировании на языке Visual Basic или C# необходимо объявлять функции DLL в классе или модуле Visual Basic.  
  
 В классе определяется статический метод для каждой функции DLL, которую требуется вызывать. Определение может включать дополнительные сведения, в том числе кодировку или соглашение о вызовах, используемые при передаче аргументов метода. Если эти сведения не указаны, используются параметры по умолчанию. Полный список параметров объявления и их значений по умолчанию см. в разделе [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
 После упаковки можно вызывать методы в классе, как вызывать статические методы для любого другого класса. При вызове неуправляемого кода базовая экспортированная функция обрабатывается автоматически.  
  
 При разработке управляемого класса для вызова неуправляемого кода следует учитывать отношения между классами и функциями DLL. Например, с их помощью можно выполнять следующее.  
  
-   Объявлять функции DLL в существующем классе.  
  
-   Создавать отдельный класс для каждой функции DLL, обеспечивая изоляцию и удобство поиска функций.  
  
-   Создавать один класс для набора связанных функций DLL, что позволяет упорядочивать их по логическим группам и снизить затраты на ресурсы.  
  
 Имена класса и его методов могут быть произвольными. Примеры, демонстрирующие создание объявлений на основе .NET, которые используются с вызовом неуправляемого кода, см. в разделе [Маршалинг данных при вызове неуправляемого кода](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>См. также  
 [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [Идентификация функций в библиотеках DLL](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [Создание прототипов в управляемом коде](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Вызов функции DLL](../../../docs/framework/interop/calling-a-dll-function.md)
