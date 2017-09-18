---
title: "Взаимодействие с неуправляемым кодом"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ff86b062efddde6f97555efb97247f60a6e1db98
ms.contentlocale: ru-ru
ms.lasthandoff: 09/18/2017

---
# <a name="interoperating-with-unmanaged-code"></a>Взаимодействие с неуправляемым кодом
Платформа .NET Framework обеспечивает взаимодействие с COM-компонентами, службами COM+, внешними библиотеками типов и многими службами операционной системы. Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов. Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.  
  
 Код, выполняющийся под управлением среды выполнения, называется управляемым кодом. И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом. Примерами неуправляемого кода являются компоненты COM, интерфейсы ActiveX и функции Win32 API.  
  
## <a name="in-this-section"></a>Содержание  
 [Разделы практических руководств, описывающие взаимодействие с неуправляемым кодом](http://msdn.microsoft.com/en-us/ec21c6e1-e233-4cd9-95ae-b9b9cf807f9d)  
 Содержит ссылки на все разделы практического руководства в основной документации по взаимодействию с неуправляемым кодом.  
  
 [Предоставление COM-компонентов платформе .NET Framework](../../../docs/framework/interop/exposing-com-components.md)  
 Описывает способы использования COM-компонентов в приложениях .NET Framework.  
  
 [Предоставление компонентов .NET Framework клиентам COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Описывает способы использования компонентов .NET Framework в приложениях COM.  
  
 [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.  
  
 [Вопросы разработки для взаимодействия](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 Приводятся советы по написанию кода встроенных COM-компонентов.  
  
 [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)  
 Описывается маршалинг для COM-взаимодействия и вызова платформы.  
  
 [Практическое руководство. Сопоставление значений HRESULT и исключений](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)  
 Описывает сопоставление исключений и значений HRESULT.  
  
 [Взаимодействие с помощью универсальных типов](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Описывает поведение универсальных типов при использовании в COM-взаимодействии.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Расширенное COM-взаимодействие](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Приводятся ссылки на дополнительные сведения о включении COM-компонентов в разрабатываемое приложение .NET Framework.

