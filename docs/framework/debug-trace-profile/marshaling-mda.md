---
title: MDA маршалинг
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
caps.latest.revision: ''
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 83b621f78e3ba4641540f6125ed14d600cc292d1
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="marshaling-mda"></a><span data-ttu-id="3c294-102">MDA маршалинг</span><span class="sxs-lookup"><span data-stu-id="3c294-102">marshaling MDA</span></span>
<span data-ttu-id="3c294-103">Помощник по отладке управляемого кода (MDA) `marshaling`активируется, когда среда CLR задает сведения о маршалинге для параметра метода или поля структуры.</span><span class="sxs-lookup"><span data-stu-id="3c294-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="3c294-104">Данный MDA не работает для сборок JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="3c294-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3c294-105">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="3c294-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="3c294-106">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="3c294-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3c294-107">Вывод</span><span class="sxs-lookup"><span data-stu-id="3c294-107">Output</span></span>  
 <span data-ttu-id="3c294-108">MDA отображает тип параметра или поля в управляемом и неуправляемом контекстах, а также структуру или метод, содержащий этот тип.</span><span class="sxs-lookup"><span data-stu-id="3c294-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="3c294-109">Ниже представлен пример выходных данных для поля.</span><span class="sxs-lookup"><span data-stu-id="3c294-109">The following is an example of the output for a field:</span></span>  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="3c294-110">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="3c294-110">Configuration</span></span>  
 <span data-ttu-id="3c294-111">Конфигурация MDA позволяет фильтровать сообщенные сведения о маршалинге на основе связанных полей или имен методов.</span><span class="sxs-lookup"><span data-stu-id="3c294-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="3c294-112">В следующем примере показано использование элементов `methodFilter`, `fieldFilter` и `match` для определения фильтров.</span><span class="sxs-lookup"><span data-stu-id="3c294-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="3c294-113">Установка звездочки (\*) в атрибуте `name` означает, что будут соответствовать все элементы.</span><span class="sxs-lookup"><span data-stu-id="3c294-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c294-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3c294-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="3c294-115">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="3c294-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="3c294-116">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="3c294-116">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
