---
title: "How to: Reference .NET Types from COM | Microsoft Docs"
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
  - "importing type library"
  - "COM interop, referencing .NET types"
  - "interoperation with unmanaged code, referencing .NET types"
  - "referencing .NET types"
  - "interoperation with unmanaged code, importing type library"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# How to: Reference .NET Types from COM
С точки зрения программного кода клиента и сервера, различия между COM и .NET Framework почти незаметны.  Клиенты Microsoft Visual Basic могут просматривать объект .NET в обозревателе объектов, который предоставляет сведения об методах и синтаксисе, свойствах и полях объекта так же, как если бы он был любым другим объектом COM.  
  
 Процесс импорта библиотеки типов для клиентов C\+\+ несколько сложнее, хотя для экспорта метаданных в библиотеку COM\-типов используются те же средства.  Для ссылки к членам объекта .NET из неуправляемого клиента C\+\+ нужно сослаться на TLB\-файл \(созданный программой Tlbexp.exe\) с помощью директивы **\#import**.  При ссылке на библиотеку типов из C\+\+ следует либо задать параметр **raw\_interfaces\_only**, либо импортировать определения из библиотеки базовых классов Mscorlib.tlb.  
  
### Импортировать библиотеку  
  
-   Задайте параметр **raw\_interfaces\_only** в директиве **\#import**.  Например:  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     \-или\-  
  
-   Включите директиву \#import для Mscorlib.tlb.  Например:  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## См. также  
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Calling a .NET Object](http://msdn.microsoft.com/ru-ru/40c9626c-aea6-4bad-b8f0-c1de462efd33)   
 [Deploying an Application for COM Access](http://msdn.microsoft.com/ru-ru/fb63564c-c1b9-4655-a094-a235625882ce)