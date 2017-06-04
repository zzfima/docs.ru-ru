---
title: "How to: Generate Interop Assemblies from Type Libraries | Microsoft Docs"
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
  - "interop assemblies, generating"
  - "Type Library Importer"
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# How to: Generate Interop Assemblies from Type Libraries
[Программа импорта библиотеки типов \(Tlbimp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) — это средство командной строки, преобразующее компонентные классы и интерфейсы, содержащиеся в библиотеке COM\-типов, в метаданные.  Этот инструмент автоматически создает сборку взаимодействия и пространство имен для сведений о типах.  После того, как метаданные класса становятся доступны, управляемые клиенты могут создавать экземпляры COM\-типа и вызывать его методы так же, как если бы это был экземпляр .NET.  Программа Tlbimp.exe преобразует в метаданные сразу всю библиотеку типов и не может создавать сведения о типах для подмножества определенных в библиотеке типов.  
  
### Создание сборки взаимодействия из библиотеки типов  
  
1.  Используйте следующую команду:  
  
     **tlbimp** \<*файл\-библиотеки\-типов*\>  
  
     Добавление переключателя **\/out:** создает сборку взаимодействия с измененным именем, например LOANLib.dll.  Изменение имени сборки взаимодействия может помочь отличить ее от исходной DLL\-библиотеки COM и предотвращает появление проблем, вызванных одинаковыми именами.  
  
## Пример  
 Следующая команда создает сборку Loanlib.dll в пространстве имен `Loanlib`.  
  
```  
tlbimp Loanlib.dll  
```  
  
 Следующая команда создает сборку взаимодействия с измененным именем \(LOANLib.dll\).  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## См. также  
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)