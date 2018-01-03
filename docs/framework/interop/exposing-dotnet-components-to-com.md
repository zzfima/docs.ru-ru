---
title: "Предоставление COM-клиентам доступа к компонентам .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing .NET Framework components to COM
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: e42a65f7-1e61-411f-b09a-aca1bbce24c6
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61e1dbdcf919ee6aa2150e6a57cb88a8aa859efe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-net-framework-components-to-com"></a>Предоставление COM-клиентам доступа к компонентам .NET Framework
Написание типа .NET и его использование из неуправляемого кода — это разные операции с точки зрения разработчика. В этом разделе приводятся советы по написанию управляемого кода, который взаимодействует с клиентами COM:  
  
-   [Уточнение типов .NET для взаимодействия](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md).  
  
     Все управляемые типы, методы, свойства, поля и события, которые требуется предоставить модели COM, должны быть открытыми. Типы должны иметь открытый конструктор по умолчанию, который является единственным конструктором, доступным для вызова из модели COM.  
  
-   [Применение атрибутов взаимодействия](../../../docs/framework/interop/applying-interop-attributes.md).  
  
     С помощью настраиваемых атрибутов в управляемом коде можно расширять возможности взаимодействия для компонента.  
  
-   [Упаковка сборки для модели COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md).  
  
     Разработчикам COM-приложений могут потребоваться общие сведения о шагах, которые необходимо выполнить для развертывания ваших сборок и использования ссылок на них.  
  
 Кроме того, в этом разделе описываются задачи, связанные с использованием управляемого типа из клиента COM.  
  
#### <a name="to-consume-a-managed-type-from-com"></a>Использование управляемого типа из модели COM  
  
1.  [Регистрация сборок в COM](../../../docs/framework/interop/registering-assemblies-with-com.md).  
  
     Типы в сборке и библиотеке типов необходимо регистрировать во время разработки. Если установщик не регистрирует сборку, необходимо предоставить разработчикам COM-приложений инструкции по использованию программы Regasm.exe.  
  
2.  [Создание ссылки на типы .NET из COM](../../../docs/framework/interop/how-to-reference-net-types-from-com.md).  
  
     Разработчики COM-приложений могут использовать доступные средства и методы для ссылки на типы в сборке.  
  
3.  [Вызов объекта .NET](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33).  
  
     Разработчики COM-приложений могут вызывать методы для объектов .NET так же, как и методы для любого неуправляемого типа. Например, API **CoCreateInstance** модели COM активирует объекты .NET.  
  
4.  [Развертывание приложения для доступа к COM-приложению](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce).  
  
     Сборки со строгими именами могут устанавливаться в глобальный кэш сборок и должны быть подписаны их издателем. Сборки, которые не имеют строгих имен, должны устанавливаться в каталог приложения клиента.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие с неуправляемым кодом](../../../docs/framework/interop/index.md)  
 [Пример COM-взаимодействия. COM-клиент и сервер .NET](../../../docs/framework/interop/com-interop-sample-com-client-and-net-server.md)
