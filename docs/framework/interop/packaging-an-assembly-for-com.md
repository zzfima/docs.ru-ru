---
title: "Packaging an Assembly for COM | Microsoft Docs"
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
  - "COM interop, packaging assemblies"
  - "packaging assemblies for COM"
  - "Tlbexp.exe"
  - "TypeLibConverter class"
  - ".NET Services Installation tool"
  - "Assembly Registration tool"
  - "Type Library Exporter"
  - "Reqsvcs.exe"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "interoperation with unmanaged code, packaging assemblies"
  - "COM interop, exposing COM components"
  - "Reqasm.exe"
ms.assetid: 39dc55aa-f2a1-4093-87bb-f1c0edb6e761
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Packaging an Assembly for COM
Разработчики COM могут воспользоваться приводящимися ниже сведениями об управляемых типах, которые они собираются включить в свои приложения:  
  
-   Перечень типов, которые могут использовать COM\-приложения  
  
     Некоторые управляемые типы невидимы для модели COM, некоторые видимы, но COM не может их создавать, а некоторые являются видимыми и COM может их создавать.  Сборка может содержать любое сочетание невидимых, видимых, несоздаваемых и создаваемых типов.  Для полноты представления рекомендуется идентифицировать в сборке типы, доступ к которым требуется предоставить модели COM, особенно когда эти типы являются подмножеством типов, предоставляемых для .NET Framework.  
  
     Дополнительные сведения см. в разделе [Уточнение типов .NET для взаимодействия](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
-   Инструкции по отслеживанию версий.  
  
     Управляемые классы, реализующий интерфейс класса \(интерфейс, создаваемый COM\-взаимодействием\), подчиняются ограничениям отслеживания версий.  
  
     Рекомендации по применению интерфейсов классов см. в разделе [Введение в интерфейс класса](http://msdn.microsoft.com/ru-ru/733c0dd2-12e5-46e6-8de1-39d5b25df024).  
  
-   Инструкции по развертыванию  
  
     Сборки со строгими именами, подписанные издателем, могут быть установлены в глобальный кэш сборок.  Неподписанные сборки должны быть установлены на компьютере пользователя как закрытые сборки.  
  
     Дополнительные сведения см. в разделе [Вопросы безопасности сборки](../../../docs/framework/app-domains/assembly-security-considerations.md).  
  
-   Включение библиотеки типов  
  
     Большинство типов, используемых в COM\-приложении, требует наличия библиотеки типов.  Библиотеку типов можно либо создать заранее, либо предоставить выполнить эту задачу разработчикам COM\-приложений.  [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] предоставляет следующие возможности создания библиотеки типов:  
  
    -   [Программа экспорта библиотек типов](#cpconpackagingassemblyforcomanchor1)  
  
    -   [Класс TypeLibConverter](#cpconpackagingassemblyforcomanchor2)  
  
    -   [Средство регистрации сборок](#cpconpackagingassemblyforcomanchor3)  
  
    -   [Средство установки служб .NET](#cpconpackagingassemblyforcomanchor4)  
  
     Независимо от выбранного механизма в создаваемую библиотеку типов включаются только открытые типы, определенные в предоставленной сборке.  
  
     Библиотеку типов можно упаковать в отдельный файл или встроить как файл ресурсов Win32 в .NET\-приложение.  Microsoft Visual Basic 6.0 выполняет эту задачу автоматически. Но при использовании [!INCLUDE[vbprvbext](../../../includes/vbprvbext-md.md)] библиотеку типов придется встроить вручную.  Инструкции см. в разделе [Практическое руководство. Библиотеки типов, встроенные в приложения .NET как ресурсы Win32](http://msdn.microsoft.com/ru-ru/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44).  
  
<a name="cpconpackagingassemblyforcomanchor1"></a>   
## Программа экспорта библиотек типов  
 [Программа экспорта библиотек типов \(Tlbexp.exe\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) является средством командной строки, преобразующим классы и интерфейсы, содержащиеся в сборке, в библиотеку COM\-типов.  После того, как сведения о типах класса становятся доступны, COM\-клиенты могут создавать экземпляры класса .NET и вызывать методы экземпляра так же, как если бы это был COM\-объект.  Tlbexp.exe выполняет преобразование сразу всей сборки.  Программу Tlbexp.exe нельзя использовать с целью генерации сведений о типах для подмножества типов, определенных в сборке.  
  
<a name="cpconpackagingassemblyforcomanchor2"></a>   
## Класс TypeLibConverter  
 Класс <xref:System.Runtime.InteropServices.TypeLibConverter>, находящийся в пространстве имен **System.Runtime.Interop**, преобразует классы и интерфейсы, содержащиеся в сборке, в библиотеку COM\-типов.  Этот интерфейс API создает те же сведения о типе, что и программа экспорта библиотек типов, описанная в предыдущем разделе.  
  
 **Класс TypeLibConverter** реализует [интерфейс ITypeLibConverter](frlrfSystemRuntimeInteropServicesITypeLibConverterClassTopic).  
  
<a name="cpconpackagingassemblyforcomanchor3"></a>   
## Средство регистрации сборок  
 [Программа регистрации сборок \(Regasm.exe\)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) может создавать и регистрировать библиотеку типов, когда разработчик применяет параметр **\/tlb:**.  Для работы COM\-клиентов требуется, чтобы библиотеки типов были установлены в системном реестре Windows.  Без этого параметра программа Regasm.exe регистрирует только типы в сборке, но не библиотеку типов.  Регистрация типов сборки и регистрация библиотеки типов — это разные операции.  
  
<a name="cpconpackagingassemblyforcomanchor4"></a>   
## Средство установки служб .NET  
 [Программа установки служб .NET \(Regsvcs.exe\)](../../../docs/framework/tools/regsvcs-exe-net-services-installation-tool.md) добавляет управляемые классы к службам компонентов Windows 2000 и объединяет несколько задач в одном инструменте.  Кроме загрузки и регистрации сборки, программа Regsvcs.exe может создавать, регистрировать и устанавливать библиотеки типов в существующие приложения COM\+ 1.0.  
  
## См. также  
 <xref:System.Runtime.InteropServices.TypeLibConverter>   
 <xref:System.Runtime.InteropServices.ITypeLibConverter>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Qualifying .NET Types for Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Introducing the Class Interface](http://msdn.microsoft.com/ru-ru/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Вопросы безопасности сборок](../../../docs/framework/app-domains/assembly-security-considerations.md)   
 [Tlbexp.exe \(Type Library Exporter\)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)   
 [Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [How to: Embed Type Libraries as Win32 Resources in Applications](http://msdn.microsoft.com/ru-ru/c97b4b8c-2ab7-4ac7-8fc8-0ba5c5d59c44)