---
title: "How to: Add References to Type Libraries | Microsoft Docs"
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
  - "type libraries"
  - "COM interop, importing type library"
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Add References to Type Libraries
При добавлении ссылки на библиотеку типов Visual Studio генерирует сборку взаимодействия, в которой содержатся метаданные.  Если первичная сборка взаимодействия доступна, Visual Studio обращается к существующей сборке, прежде чем генерировать новую.  
  
### Добавление ссылки на библиотеку типов в Visual Studio  
  
1.  Если файл Windows Setup.exe не осуществит установку автоматически, установите DLL\- или EXE\-файл COM на компьютер.  
  
2.  Выберите **Проект**, **Добавить ссылку**.  
  
3.  В Диспетчере ссылок выберите **COM**.  
  
4.  Выберите библиотеку типов из списка или найдите файл с расширением .TLB.  
  
5.  Нажмите кнопку **ОК**.  
  
6.  В Обозревателе решений откройте контекстное меню добавленной ссылки и выберите **Свойства**.  
  
7.  Убедитесь, что свойство **Внедрить типы взаимодействия** в окне **Свойства**  имеет значение **True**.  Visual Studio внедрит информацию о типах COM в исполняемые файлы, устранив тем самым необходимость развертывать основные сборки взаимодействия в приложении.  
  
> [!NOTE]
>  Пункты меню и параметры диалогового окна зависят от используемой версии Visual Studio.  
  
### Добавление ссылки на библиотеку типов для компиляции командной строки  
  
1.  Сгенерируйте сборку взаимодействия, как описано в разделе [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
2.  Для внедрения информации о типах COM в исполняемые файлы используйте параметр компилятора [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md) или [\/link](../Topic/-link%20\(Visual%20Basic\).md) с именем сборки взаимодействия.  
  
## См. также  
 [Importing a Type Library as an Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](../Topic/Walkthrough:%20Embedding%20Types%20from%20Managed%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [\/link \(Link to COM Assembly\)](../Topic/-link%20\(C%23%20Compiler%20Options\).md)   
 [\/link](../Topic/-link%20\(Visual%20Basic\).md)