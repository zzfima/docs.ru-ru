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
# <a name="marshaling-mda"></a>MDA маршалинг
Помощник по отладке управляемого кода (MDA) `marshaling`активируется, когда среда CLR задает сведения о маршалинге для параметра метода или поля структуры. Данный MDA не работает для сборок JIT-компиляции.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Вывод  
 MDA отображает тип параметра или поля в управляемом и неуправляемом контекстах, а также структуру или метод, содержащий этот тип.  Ниже представлен пример выходных данных для поля.  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a>Конфигурация  
 Конфигурация MDA позволяет фильтровать сообщенные сведения о маршалинге на основе связанных полей или имен методов.  В следующем примере показано использование элементов `methodFilter`, `fieldFilter` и `match` для определения фильтров.  Установка звездочки (*) в атрибуте `name` означает, что будут соответствовать все элементы.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Маршалинг взаимодействия](../../../docs/framework/interop/interop-marshaling.md)
