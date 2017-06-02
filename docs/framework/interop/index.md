---
title: "Interoperating with Unmanaged Code | Microsoft Docs"
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
  - "unmanaged code, interoperation"
  - "managed code, interoperation with unmanaged code"
  - ".NET Framework, interoperation with unmanaged code"
  - "unmanaged code"
  - "interoperation with unmanaged code"
  - "interoperation with unmanaged code, about interoperation"
  - "components [.NET Framework], interoperation with unmanaged code"
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Interoperating with Unmanaged Code
Платформа .NET Framework обеспечивает взаимодействие с COM\-компонентами, службами COM\+, внешними библиотеками типов и многими службами операционной системы.  Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов.  Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.  
  
 Программный код, выполняющийся под управлением среды выполнения, называется управляемым кодом.  И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом.  Примерами неуправляемого программного кода могут служить COM\-компоненты, интерфейсы ActiveX и функции интерфейса Win32 API.  
  
## В этом подразделе  
 [Interoperating with Unmanaged Code How\-to Topics](http://msdn.microsoft.com/ru-ru/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Содержит ссылки на разделы практического руководства в основной документации по взаимодействию с неуправляемым кодом.  
  
 [Предоставление клиентам .NET Framework доступа к COM\-компонентам](../../../docs/framework/interop/exposing-com-components.md)  
 Описывает способы использования COM\-компонентов в приложениях .NET Framework.  
  
 [Предоставление COM\-клиентам доступа к компонентам .NET Framework](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Описывает способы использования компонентов .NET Framework в приложениях COM.  
  
 [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Описывает способ вызова неуправляемых функций DLL с помощью вызова неуправляемого кода.  
  
 [Вопросы разработки для взаимодействия](http://msdn.microsoft.com/ru-ru/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Содержит советы по написанию кода встроенных COM\-компонентов.  
  
 [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)  
 Описывает маршалинг для COM\-взаимодействия и вызовов неуправляемого кода.  
  
 [How to: Map HRESULTs and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Описывает соответствие исключений и значений HRESULT.  
  
 [Interoperating Using Generic Types](http://msdn.microsoft.com/ru-ru/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Описывает поведение универсальных типов при использовании в COM\-взаимодействии.  
  
## Связанные подразделы  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ru-ru/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Содержит ссылки на дополнительные сведения о включении COM\-компонентов в разрабатываемое приложение .NET Framework.