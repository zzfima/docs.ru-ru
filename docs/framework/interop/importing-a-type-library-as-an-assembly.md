---
title: "Importing a Type Library as an Assembly | Microsoft Docs"
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
  - "type metadata"
  - "custom wrappers"
  - "metadata"
  - "exposing COM components to .NET Framework"
  - "Type Library Importer"
  - "interoperation with unmanaged code, importing type library"
  - "interoperation with unmanaged code, exposing COM components"
  - "type libraries"
  - "TypeLibConverter class, importing type library as assembly"
  - "COM interop, importing type library"
  - "COM interop, exposing COM components"
ms.assetid: d1898229-cd40-426e-a275-f3eb65fbc79f
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Importing a Type Library as an Assembly
Определения COM\-типов обычно хранятся в библиотеке типов.  С другой стороны, CLS\-совместимые компиляторы создают в сборке метаданные типов.  Эти два источника сведений о типе заметно отличаются.  В этом разделе описываются способы создания метаданных из библиотеки типов.  Полученная сборка называется сборкой взаимодействия, и содержащаяся в ней информация о типах позволяет приложениям платформы .NET Framework использовать типы COM.  
  
 Есть два способа предоставить приложению эту информацию о типах:  
  
-   С использованием сборок взаимодействия только на этапе проектирования: начиная с платформы [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], можно указать компилятору, что в исполняемый файл следует внедрить информацию о типах из сборки взаимодействия.  Компилятор встраивает информацию только о типах, используемых приложением.  Развертывать сборку взаимодействия вместе с приложением не требуется.  Это рекомендуемая методика.  
  
-   Путем развертывания сборок взаимодействия: можно создать стандартную ссылку на сборку взаимодействия.  В данном случае сборку взаимодействия следует развернуть вместе с приложением.  Если применяется данный метод и не используется частный COM\-компонент, необходимо во всех случаях ссылаться на основную сборку взаимодействия, опубликованную автором COM\-компонента, который планируется интегрировать в управляемый код.  Дополнительные сведения о создании и использовании основных сборок взаимодействия см. в разделе [Основные сборки взаимодействия](http://msdn.microsoft.com/ru-ru/b977a8be-59a0-40a0-a806-b11ffba5c080).  
  
 При использовании сборок взаимодействия только во время проектирования можно встраивать информацию о типах из основной сборки взаимодействия, опубликованной автором COM\-компонента.  Развертывать основную сборку взаимодействия вместе с приложением при этом не требуется.  
  
 Использование сборок взаимодействия только во время проектирования сокращает размер приложения, поскольку большинство приложений используют лишь некоторые функции компонентов COM.  Компилятор весьма эффективно внедряет информацию о типах: если приложение использует лишь некоторые методы интерфейса COM, то компилятор не будет встраивать неиспользуемые методы.  Если приложение со внедренной информацией о типах взаимодействует с другим аналогичным приложением или приложением, использующим основную сборку взаимодействия, то среда CLR использует правила эквивалентности типов, чтобы определить, представляют ли одноименные типы один и тот же тип COM.  Необязательно знать эти правила, чтобы использовать объекты COM.  Тем не менее, сведения о них можно найти в разделе [Type Equivalence and Embedded Interop Types](../../../docs/framework/interop/type-equivalence-and-embedded-interop-types.md).  
  
## Создание метаданных  
 Библиотеки COM\-типов могут быть автономными TLB\-файлами, например Loanlib.tlb.  Некоторые библиотеки типов встроены в раздел ресурсов файла DLL или EXE.  Другими источниками данных библиотек типов являются файлы OLB и OCX.  
  
 После обнаружения библиотеки типов, содержащей реализацию искомого COM\-типа, для создания сборки взаимодействия, содержащей метаданные типа, разработчик может выбрать нужный из нескольких вариантов.  
  
-   Visual Studio  
  
     Visual Studio автоматически преобразует COM\-типы библиотеки типов в метаданные сборки.  Инструкции см. в разделах [Практическое руководство. Добавление ссылок на библиотеки типов](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md) и [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md).  
  
-   [Программа экспорта библиотек типов \(Tlbexp.exe\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)  
  
     Программа экспорта библиотек типов предоставляет параметры командной строки для настройки метаданных в результирующем файле взаимодействия, импортирует типы из существующей библиотеки типов и создает сборку взаимодействия и пространство имен.  Инструкции см. в разделе [Практическое руководство. Создание сборок взаимодействия их библиотек типов](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md).  
  
-   Класс <xref:System.Runtime.InteropServices.TypeLibConverter?displayProperty=fullName>  
  
     Этот класс предоставляет методы для преобразования компонентных классов и интерфейсов из библиотеки типов в метаданные внутри сборки.  При этом создаются те же метаданные, что и в программе Tlbimp.exe.  Однако же в отличие от Tlbimp.exe класс <xref:System.Runtime.InteropServices.TypeLibConverter> может преобразовать в метаданные библиотеку типов, находящуюся в памяти.  
  
-   Настраиваемые оболочки  
  
     Если библиотека типов недоступна или является неверной, единственный выход — создать в управляемом исходном коде дубликат определения класса или интерфейса.  После этого нужно скомпилировать исходный код с помощью компилятора, который обращается к среде выполнения, чтобы создать метаданные в сборке.  
  
     Чтобы определить COM\-типы вручную, необходим доступ к следующим элементам:  
  
    -   точные описания определяемых компонентных классов и интерфейсов;  
  
    -   компилятор, например, компилятор C\#, который может создавать соответствующие определения классов .NET Framework;  
  
    -   сведения о правилах преобразования библиотек типов в сборки.  
  
     Создание настраиваемой оболочки — это сложная процедура.  Дополнительные сведения о создании настраиваемых оболочек см. в разделе [Настройка стандартных оболочек](http://msdn.microsoft.com/ru-ru/c40d089b-6a3c-41b5-a20d-d760c215e49d).  
  
 Дополнительные сведения о процессе импорта COM\-взаимодействия см. в разделе [Общие сведения о преобразовании библиотеки типов в сборку](http://msdn.microsoft.com/ru-ru/bf3f90c5-4770-4ab8-895c-3ba1055cc958).  
  
## См. также  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 [Exposing COM Components to the .NET Framework](../../../docs/framework/interop/exposing-com-components.md)   
 [Type Library to Assembly Conversion Summary](http://msdn.microsoft.com/ru-ru/bf3f90c5-4770-4ab8-895c-3ba1055cc958)   
 [Tlbimp.exe \(Type Library Importer\)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/ru-ru/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [Using COM Types in Managed Code](http://msdn.microsoft.com/ru-ru/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66)   
 [Compiling an Interop Project](../../../docs/framework/interop/compiling-an-interop-project.md)   
 [Deploying an Interop Application](../../../docs/framework/interop/deploying-an-interop-application.md)   
 [How to: Add References to Type Libraries](../../../docs/framework/interop/how-to-add-references-to-type-libraries.md)   
 [How to: Generate Interop Assemblies from Type Libraries](../../../docs/framework/interop/how-to-generate-interop-assemblies-from-type-libraries.md)   
 [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](../Topic/Walkthrough:%20Embedding%20Type%20Information%20from%20Microsoft%20Office%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)