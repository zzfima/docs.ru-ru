---
title: Переадресация типов в общеязыковой среде CLR
ms.date: 03/30/2017
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1b05a5548beb7e7c1f0ec8e96b6e02350318ef9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921417"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a>Переадресация типов в общеязыковой среде CLR
Перенаправление типа позволяет переместить тип в другую сборку без повторной компиляции приложений, использующих исходную сборку.  
  
 Предположим, например, что приложение использует класс `Example` в сборке с именем `Utility.dll`. Разработчики `Utility.dll` могут принять решение выполнить рефакторинг сборки и в ходе этого процесса могут переместить класс `Example` в другую сборку. Если старую версию `Utility.dll` заменить новой версией `Utility.dll` и ее сопутствующей сборкой, приложение, использующее класс `Example`, завершится ошибкой, поскольку не сможет найти класс `Example` в новой версии `Utility.dll`.  
  
 Разработчики `Utility.dll` могут избежать этого, перенаправляя запросы к классу `Example` с помощью атрибута <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>. Если атрибут применен к новой версии `Utility.dll`, запросы класса `Example` перенаправляются в сборку, которая теперь содержит этот класс. Существующее приложение продолжает нормально функционировать без перекомпиляции.  
  
> [!NOTE]
> В платформе .NET Framework версии 2.0 нельзя перенаправлять типы из сборок, написанных на Visual Basic. Тем не менее приложения, написанные на Visual Basic, могут использовать перенаправленные типы. То есть если приложение использует сборку, написанную на языке C# или C++, и тип из этой сборки перенаправляется в другую сборку, приложение Visual Basic можно использовать перенаправленный тип.  
  
## <a name="forwarding-types"></a>Перенаправление типов  
 Для перенаправления типа следует выполнить следующую процедуру.  
  
1. Переместите исходный код для типа из исходной сборки в целевую сборку.  
  
2. В сборке, где раньше находился тип, добавьте <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> для типа, который был перемещен. В следующем коде показан атрибут для типа с именем `Example`, который был перемещен.  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3. Скомпилируйте сборку, которая теперь содержит тип.  
  
4. Перекомпилируйте сборку, где раньше находился тип, со ссылкой на сборку, которая теперь содержит тип. Например, при компиляции файла C# из командной строки используйте параметр [/reference (параметры компилятора C#)](../../csharp/language-reference/compiler-options/reference-compiler-option.md), чтобы указать сборку, содержащую тип. В C++ используйте директиву [#using](/cpp/preprocessor/hash-using-directive-cpp) в исходном файле, чтобы указать сборку, содержащую тип.  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [Перенаправление типов (C++/CLI)](/cpp/windows/type-forwarding-cpp-cli)
- [Директива #using](/cpp/preprocessor/hash-using-directive-cpp)
