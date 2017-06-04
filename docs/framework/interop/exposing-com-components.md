---
title: "Exposing COM Components to the .NET Framework | Microsoft Docs"
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
  - "exposing COM components to .NET Framework"
  - "interoperation with unmanaged code, exposing COM components"
  - "COM interop, exposing COM components"
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Exposing COM Components to the .NET Framework
В этом разделе обобщается процесс предоставления управляемому коду доступа к существующему COM\-компоненту.  Дополнительные сведения о написании COM\-серверов, тесно связанных с .NET Framework, см. в разделе [Вопросы проектирования взаимодействия](http://msdn.microsoft.com/ru-ru/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Существующие COM\-компоненты могут представлять собой ценные ресурсы для управляемого кода в качестве бизнес\-приложений промежуточного уровня или изолированных функциональных возможностей.  В идеале компонент должен содержать основную сборку взаимодействия и строго соответствовать стандартам программирования COM.  
  
#### Предоставление .NET Framework доступа к COM\-компонентам  
  
1.  [Импорт библиотеки типов в качестве сборки](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Среда CLR требует наличия метаданных для всех типов, включая COM\-типы.  Существует несколько путей получения сборки, содержащей COM\-типы, импортируемые как метаданные.  
  
2.  [Создание COM\-типов в управляемом коде](http://msdn.microsoft.com/ru-ru/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Разработчик может проверять COM\-типы, активировать экземпляры и вызывать методы для COM\-объекта точно так же, как и для любого управляемого типа.  
  
3.  [Компиляция проекта взаимодействия](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] предоставляет компиляторы для нескольких языков, совместимых со спецификацией CLS, включая [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# и C\+\+.  
  
4.  [Развертывание приложения взаимодействия](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Приложения взаимодействия лучше всего распространять как подписанные сборки со [строгими именами](../../../docs/framework/app-domains/strong-named-assemblies.md), в глобальном кэше сборок.  
  
## См. также  
 [Interoperating with Unmanaged Code](../../../docs/framework/interop/index.md)   
 [Design Considerations for Interoperation](http://msdn.microsoft.com/ru-ru/b59637f6-fe35-40d6-ae72-901e7a707689)   
 [COM Interop Sample: .NET Client and COM Server](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)   
 [Независимость от языка и независимые от языка компоненты](../../../docs/standard/language-independence-and-language-independent-components.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)