---
title: Предоставление клиентам .NET Framework доступа к COM-компонентам
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 914f72b5e4840555541943620ca2df1f629b0604
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123528"
---
# <a name="exposing-com-components-to-the-net-framework"></a>Предоставление клиентам .NET Framework доступа к COM-компонентам
В этом разделе описывается процесс, в рамках которого существующий COM-компонент предоставляется управляемому коду. Сведения о разработке COM-серверов, которые тесно интегрируются с платформой .NET Framework, см. в разделе [Вопросы разработки для взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).
  
 Существующие COM-компоненты являются ценными ресурсами для управляемого кода, выступая в качестве бизнес-приложений среднего уровня или изолированных функций. В идеале компонент содержит основную сборку взаимодействия и строго соответствует стандартам программирования модели COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Предоставление клиентам .NET Framework доступа к COM-компонентам  
  
1. [Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md).  
  
     Общеязыковая среда выполнения требует наличия метаданных для всех типов, включая COM-типы. Получить сборку, содержащую импортированные COM-типы, в виде метаданных можно несколькими способами.  
  
2. [Использование типов COM в управляемом коде](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).  
  
     Вы можете проверять COM-типы, активировать экземпляры и вызывать методы COM-объекта так же, как и для любого другого управляемого типа.  
  
3. [Компиляция проекта, использующего взаимодействие](compiling-an-interop-project.md).  
  
     Windows SDK предоставляет компиляторы для нескольких языков, соответствующих требованиям спецификации общеязыковой среды выполнения (CLS), включая Visual Basic, C# и C++.  
  
4. [Развертывание приложения взаимодействия](deploying-an-interop-application.md).  
  
     Приложения взаимодействия рекомендуется развертывать в виде подписанных сборок со [строгими именами](../../standard/assembly/strong-named.md) в глобальном кэше сборок.  
  
## <a name="see-also"></a>См. также

- [Взаимодействие с неуправляемым кодом](index.md)
- [Вопросы разработки для взаимодействия](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))
- [Пример COM-взаимодействия. Клиент .NET и COM-сервер](com-interop-sample-net-client-and-com-server.md)
- [Независимость от языка и независимые от языка компоненты](../../standard/language-independence-and-language-independent-components.md)
- [Gacutil.exe (программа глобального кэша сборок)](../tools/gacutil-exe-gac-tool.md)
