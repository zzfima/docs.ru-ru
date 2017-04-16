---
title: "Calling a DLL Function | Microsoft Docs"
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
  - "unmanaged functions, calling"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "platform invoke, calling unmanaged functions"
  - "interoperation with unmanaged code, platform invoke"
  - "DLL functions"
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Calling a DLL Function
Хотя вызов неуправляемых функций DLL почти идентичен вызову другого управляемого кода, все же существуют отличия, которые поначалу могут вызвать некоторые сложности в освоении функций DLL.  В этом разделе представлены темы, касающиеся некоторых особенностей вызовов.  
  
 Структуры, возвращаемые из вызовов неуправляемого кода, должны быть типами данных, имеющими одинаковые представления в управляемом и неуправляемом кодах.  Такие типы называются *непреобразуемыми типами*, так как они не требуют преобразования \(см. [Blittable and Non\-Blittable Types](../../../docs/framework/interop/blittable-and-non-blittable-types.md)\).  Чтобы вызвать функцию с преобразуемой структурой как ее возвращаемый тип, можно определить непреобразуемый вспомогательный тип того же размера, что и преобразуемый тип, и преобразовать данные после возвращения функции.  
  
## В этом подразделе  
 [Передача структур](../../../docs/framework/interop/passing-structures.md)  
 Определяет вопросы передачи структур данных с предопределенной компоновкой.  
  
 [Функции обратного вызова](../../../docs/framework/interop/callback-functions.md)  
 Предоставляет базовые сведения о функциях обратного вызова.  
  
 [Практическое руководство. Реализация функций обратного вызова](../../../docs/framework/interop/how-to-implement-callback-functions.md)  
 Описывает порядок реализации функций обратного вызова в управляемом коде.  
  
## Связанные подразделы  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Описывает способ вызова неуправляемых функций DLL с помощью вызова неуправляемого кода.  
  
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)  
 Описывает способ объявления параметров метода и передачи аргументов в функции, экспортируемые неуправляемыми библиотеками.