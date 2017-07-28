---
title: "Qualifying .NET Types for Interoperation | Microsoft Docs"
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
  - "exposing .NET Framework components to COM"
  - "COM interop, qualifying .NET types"
  - "qualifying .NET types for interoperation"
  - "interoperation with unmanaged code, qualifying .NET types"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Qualifying .NET Types for Interoperation
Если требуется предоставить типы из сборки COM\-приложению, в режиме разработки следует учитывать требования COM\-взаимодействия.  Управляемые типы \(класс, интерфейс, структура и перечисление\) легко интегрируются с COM\-типами, если строго соблюдаются следующие указания:  
  
-   Классы должны реализовать интерфейсы явным образом.  
  
     Хотя COM\-взаимодействие обеспечивает механизм автоматического создания интерфейса, содержащего все члены класса и члены базового класса, гораздо лучше предоставить явные интерфейсы.  Автоматически созданный интерфейс называется интерфейсом класса.  Указания см. в разделе [Введение в интерфейс класса](http://msdn.microsoft.com/ru-ru/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
     Для включения определений интерфейса в код разработчик может использовать [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# и C\+\+ вместо необходимости использовать язык IDL или его эквивалент.  Сведения о синтаксисе см. в документации по используемому языку.  
  
-   Управляемые типы должны быть открытыми.  
  
     Регистрируются и экспортируются в библиотеку типов только открытые типы сборки.  В результате для COM видимы только открытые типы.  
  
     Управляемые типы предоставляют свои функциональные возможности другому управляемому коду, который не может быть доступен для COM.  Например, конструкторы с параметрами, статические методы и поля констант недоступны COM\-клиентам.  Кроме того, так как среда выполнения выполняет маршалинг данных в тип и из типа, эти данные могут быть скопированы или преобразованы.  
  
-   Методы, свойства, поля и события должны быть открытыми.  
  
     Если члены открытых типов должны быть видимы для COM, они также должны быть открытыми.  Видимость сборки, открытого типа или открытых членов открытого типа можно ограничить с помощью атрибута <xref:System.Runtime.InteropServices.ComVisibleAttribute>.  По умолчанию все открытые типы и члены являются видимыми.  
  
-   Типы должны иметь открытый конструктор по умолчанию, активируемый из COM.  
  
     Управляемые открытые типы видимы для COM.  Однако без открытого конструктора по умолчанию \(конструктора без аргументов\) COM\-клиенты не могут создавать типы.  Но COM\-клиенты могут использовать тип, если он активирован некоторыми другими средствами.  
  
-   Типы не могут быть абстрактными.  
  
     Ни COM\-клиенты, ни клиенты .NET не могут создавать абстрактные типы.  
  
 При экспорте в COM иерархия наследований управляемого типа теряется.  Отслеживание версий также отличается в управляемой и неуправляемой средах.  Типы, предоставляемые COM, не поддерживают такие же возможности отслеживания версий, как другие управляемые типы.  
  
## См. также  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/ru-ru/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Applying Interop Attributes](../../../docs/framework/interop/applying-interop-attributes.md)   
 [Packaging an Assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)