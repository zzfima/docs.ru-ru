---
title: "Предоставление клиентам .NET Framework доступа к COM-компонентам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7cbef9247b82268b8006d640b967ffd03ae6717
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="exposing-com-components-to-the-net-framework"></a>Предоставление клиентам .NET Framework доступа к COM-компонентам
В этом разделе описывается процесс, в рамках которого существующий COM-компонент предоставляется управляемому коду. Сведения о разработке COM-серверов, которые тесно интегрируются с платформой .NET Framework, см. в разделе [Вопросы разработки для взаимодействия](http://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Существующие COM-компоненты являются ценными ресурсами для управляемого кода, выступая в качестве бизнес-приложений среднего уровня или изолированных функций. В идеале компонент содержит основную сборку взаимодействия и строго соответствует стандартам программирования модели COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Предоставление клиентам .NET Framework доступа к COM-компонентам  
  
1.  [Импорт библиотеки типов в виде сборки](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Общеязыковая среда выполнения требует наличия метаданных для всех типов, включая COM-типы. Получить сборку, содержащую импортированные COM-типы, в виде метаданных можно несколькими способами.  
  
2.  [Создание COM-типов в управляемом коде](http://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Вы можете проверять COM-типы, активировать экземпляры и вызывать методы COM-объекта так же, как и для любого другого управляемого типа.  
  
3.  [Компиляция проекта, использующего взаимодействие](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] предоставляет компиляторы для нескольких языков, соответствующих требованиям спецификации общеязыковой среды выполнения (CLS), включая [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# и C++.  
  
4.  [Развертывание приложения взаимодействия](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Приложения взаимодействия рекомендуется развертывать в виде подписанных сборок со [строгими именами](../../../docs/framework/app-domains/strong-named-assemblies.md) в глобальном кэше сборок.  
  
## <a name="see-also"></a>См. также  
 [Взаимодействие с неуправляемым кодом](../../../docs/framework/interop/index.md)  
 [Вопросы разработки для взаимодействия](http://msdn.microsoft.com/library/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [Пример COM-взаимодействия. Клиент .NET и COM-сервер](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [Независимость от языка и независимые от языка компоненты](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [Gacutil.exe (программа глобального кэша сборок)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
