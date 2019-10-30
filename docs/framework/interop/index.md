---
title: Взаимодействие с неуправляемым кодом
ms.date: 01/17/2018
helpviewer_keywords:
- unmanaged code, interoperation
- managed code, interoperation with unmanaged code
- .NET Framework, interoperation with unmanaged code
- unmanaged code
- interoperation with unmanaged code
- interoperation with unmanaged code, about interoperation
- components [.NET Framework], interoperation with unmanaged code
ms.assetid: ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258
ms.openlocfilehash: cdd8d2781331956289d2b74162e653ba1ee8fad6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114231"
---
# <a name="interoperating-with-unmanaged-code"></a>Взаимодействие с неуправляемым кодом

Платформа .NET Framework обеспечивает взаимодействие с COM-компонентами, службами COM+, внешними библиотеками типов и многими службами операционной системы. Типы данных, подписи методов и механизмы обработки ошибок различны в управляемой и неуправляемой моделях объектов. Для упрощения взаимодействия между компонентами .NET Framework и неуправляемым программным кодом, а также для облегчения перехода от одной модели к другой среда CLR скрывает имеющиеся в этих объектных моделях различия от клиентов и серверов.

Код, выполняющийся под управлением среды выполнения, называется управляемым кодом. И наоборот, код, выполняемый вне среды выполнения, называется неуправляемым кодом. Примерами неуправляемого кода являются компоненты COM, интерфейсы ActiveX и функции Windows API.

## <a name="in-this-section"></a>Содержание раздела

[Предоставление COM-компонентов платформе .NET Framework](exposing-com-components.md)  
Описывает способы использования COM-компонентов в приложениях .NET Framework.

[Предоставление компонентов .NET Framework клиентам COM](exposing-dotnet-components-to-com.md)  
Описывает способы использования компонентов .NET Framework в приложениях COM.

[Использование неуправляемых функций DLL](consuming-unmanaged-dll-functions.md)  
Описывает способ вызова неуправляемых функций DLL с помощью вызова платформы.

[Маршалинг взаимодействия](interop-marshaling.md)  
Описывается маршалинг для COM-взаимодействия и вызова платформы.

[Практическое руководство. Сопоставление значений HRESULT и исключений](how-to-map-hresults-and-exceptions.md)  
Описывает сопоставление исключений и значений HRESULT.

[Oболочки COM](com-wrappers.md)  
Описываются программы-оболочки, предоставляемые COM-взаимодействием.

[Эквивалентность типов и внедренные типы взаимодействия](type-equivalence-and-embedded-interop-types.md)  
Описывается способ внедрения сведений о типах COM в сборках и определения общеязыковой средой выполнения эквивалентности встроенных типов COM.

[Практическое руководство. Создание основной сборки взаимодействия с помощью программы Tlbimp.exe](how-to-generate-primary-interop-assemblies-using-tlbimp-exe.md)  
Описывается способ создания основных сборок взаимодействия с помощью *Tlbimp.exe* (программа импорта библиотек типов).

[Практическое руководство. Регистрация основных сборок взаимодействия](how-to-register-primary-interop-assemblies.md)  
Описывается регистрация основных сборок взаимодействия до того, как на них можно будет создавать ссылки в проектах.

[COM-взаимодействие без регистрации](registration-free-com-interop.md)  
Описывается способ активации COM-взаимодействием компонентов без использования реестра Windows.

[Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации](configure-net-framework-based-com-components-for-reg.md)  
Описывается способ создания манифеста приложения, а также создания и внедрения манифеста компонента.
