---
title: illegalPrepareConstrainedRegion MDA
ms.date: 03/30/2017
helpviewer_keywords:
- PrepareConstrainedRegions method
- managed debugging assistants (MDAs), illegal PrepareConstrainedRegions
- try/catch exception handling, managed debugging assistants
- IllegalPrepareConstrainedRegions MDA
- MDAs (managed debugging assistants), illegal PrepareConstrainedRegions
ms.assetid: 2f9b5031-f910-4e01-a196-f89eab313eaf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 623aff91eb801b4b32fc180bd97ed3822ad7f163
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052675"
---
# <a name="illegalprepareconstrainedregion-mda"></a>illegalPrepareConstrainedRegion MDA
Помощник по отладке управляемого кода (MDA) `illegalPrepareConstrainedRegion` запускается, если сразу же после вызова метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A?displayProperty=nameWithType> не следует инструкция `try` обработчика исключений. Это ограничение используется на уровне MSIL, поэтому между вызовом и `try` можно размещать текст, не приводящий к созданию кода, например комментарии.  
  
## <a name="symptoms"></a>Симптомы  
 Область ограниченного выполнения, которая никогда не рассматривается в виде такой области, но представляет собой простой блок обработки исключений (`finally` или `catch`). Поэтому эта область не запускается в случае нехватки памяти или прерывания потока.  
  
## <a name="cause"></a>Причина  
 Вы не следуете шаблону подготовки для области ограниченного выполнения.  Это ошибка. / / `fault` / `catch` `finally` Вызов метода, используемый для пометки обработчиков исключений как знакомого CER`filter` в блоках, должен использоваться непосредственно перед <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> `try` оператор.  
  
## <a name="resolution"></a>Решение  
 Убедитесь, что вызов метода <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A> выполняется непосредственно перед инструкцией `try`.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.  
  
## <a name="output"></a>Вывод  
 Помощник по отладке управляемого кода отображает имя метода, вызывающего метод <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>, смещение MSIL и сообщение о том, что вызов метода выполняется не перед началом блока try.  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан шаблон, который запускает этот помощник по отладке управляемого кода.  
  
```csharp
void MethodWithInvalidPCR()  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    Object o = new Object();  
    try  
    {  
        …  
    }  
    finally  
    {  
        …  
    }  
}  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
- [Маршалинг взаимодействия](../interop/interop-marshaling.md)
