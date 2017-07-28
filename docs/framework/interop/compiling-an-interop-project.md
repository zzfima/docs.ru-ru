---
title: "Compiling an Interop Project | Microsoft Docs"
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
  - "interoperation with unmanaged code, compiling"
  - "COM interop, compiling"
  - "exposing COM components to .NET Framework"
  - "compiling interop projects"
  - "interoperation with unmanaged code, exposing COM components"
  - "COM interop, exposing COM components"
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Compiling an Interop Project
Проекты COM\-взаимодействия, которые обращаются к одной или нескольким сборкам, содержащим импортированные COM\-типы, компилируются подобно любому другому управляемому проекту.  На сборки взаимодействия можно ссылаться в среде разработки, например в Visual Studio, или при использовании компилятора командной строки.  В любом случае для правильной компиляции сборка взаимодействия должна находиться в одном каталоге с остальными файлами проекта.  
  
 Есть два способа создания ссылок на сборки взаимодействия:  
  
-   Встроенные типы взаимодействия: начиная с платформ [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], можно указать компилятору, что в исполняемый файл следует внедрить информацию о типах из сборки взаимодействия.  Это рекомендуемая методика.  
  
-   Путем развертывания сборок взаимодействия можно создать стандартную ссылку на сборку взаимодействия.  В данном случае сборку взаимодействия следует развернуть вместе с приложением.  
  
 Различия этих двух методик подробно рассмотрены в разделе [Using COM Types in Managed Code](http://msdn.microsoft.com/ru-ru/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
 Внедрение типов взаимодействия с помощью Visual Studio продемонстрировано в разделах [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md) и [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Чтобы создать ссылку на сборку взаимодействия с помощью компилятора с интерфейсом командной строки и внедрить сведения о типах в исполняемые файлы, используйте параметр компилятора [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md) или [\/link](../Topic/-link%20\(Visual%20Basic\).md) и укажите имя сборки взаимодействия.  
  
> [!NOTE]
>  Приложения Visual C\+\+ не могут внедрять сведения о типах, но могут взаимодействовать с приложениями или надстройками, которые могут внедрять такие сведения.  
  
 Для компиляции приложения, которое включает в себя основную сборку взаимодействия при развертывании, используйте параметр компилятора **\/reference** и укажите имя сборки взаимодействия.  
  
## См. также  
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Независимость от языка и независимые от языка компоненты](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ru-ru/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)