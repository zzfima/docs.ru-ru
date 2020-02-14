---
title: openGenericCERCall MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- open generic CER calls
- constrained execution regions
- openGenericCERCall MDA
- CER calls
- managed debugging assistants (MDAs), CER calls
- generics [.NET Framework], open generic CER calls
ms.assetid: da3e4ff3-2e67-4668-9720-fa776c97407e
ms.openlocfilehash: de1735103314dfedbabe27623f579ce2c1e728af
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217268"
---
# <a name="opengenericcercall-mda"></a>openGenericCERCall MDA

Помощник по отладке управляемого кода `openGenericCERCall` активируется, чтобы предупредить о том, что граф области ограниченного выполнения (CER) с переменными универсального типа в корневом методе обрабатывается во время JIT-компиляции или генерации образа в машинном коде и при этом как минимум одна из переменных универсального типа представляет собой тип ссылки на объект.

## <a name="symptoms"></a>Симптомы

Код в области ограниченного выполнения не выполняется при прерывании потока или при выгрузке домена приложения.

## <a name="cause"></a>Причина

Во время JIT-компиляции создание экземпляра типа ссылки на объект носит исключительно репрезентативный характер, поскольку полученный код будет общим, а каждая переменная типа ссылки на объект может быть любого типа ссылки на объект. Это позволяет предотвратить заблаговременную подготовку некоторых ресурсов времени выполнения.

В частности, методы с переменными универсального типа могут отложенным образом выделять ресурсы в фоновом режиме. Это записи универсального словаря. Например, для инструкции `List<T> list = new List<T>();`, где `T` является переменной универсального типа, среда выполнения должна выполнять поиск и, возможно, создать точное создание экземпляра во время выполнения, например `List<Object>, List<String>`и т. д. Этот процесс может завершаться сбоем по целому ряду причин, которые разработчик не может контролировать, например из-за нехватки памяти.

Этот помощник по отладке управляемого кода следует активировать только во время JIT-компиляции, а не при создании точного экземпляра.

Как правило, активация этого помощника по отладке управляемого кода вызвана сбоем области ограниченного выполнения для поврежденных экземпляров. Фактически среда выполнения не пытается реализовать область ограниченного выполнения в ситуации, в которой активируется этот помощник по отладке управляемого кода. Если разработчик использует общий экземпляр среды ограниченного выполнения, ошибки JIT-компиляции, ошибки загрузки универсальных типов или прерывания потоков в предполагаемой области ограниченного выполнения не перехватываются.

## <a name="resolution"></a>Решение

Не используйте переменные универсального типа, которые имеют тип ссылки на объект, в методах, которые могут содержать область ограниченного выполнения.

## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения

Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.

## <a name="output"></a>Вывод

Ниже приведен пример выходных данных из этого помощника по отладке управляемого кода.
  
 ```output
 Method 'GenericMethodWithCer', which contains at least one constrained execution region, cannot be prepared automatically since it has one or more unbound generic type parameters.
 The caller must ensure this method is prepared explicitly at run time prior to execution. 
 method name="GenericMethodWithCer"
 declaringType name="OpenGenericCERCall"
 ```

## <a name="configuration"></a>Конфигурация

```xml
<mdaConfig>
  <assistants>
    <openGenericCERCall/>
  </assistants>
</mdaConfig>
```  

## <a name="example"></a>Пример

Код в области ограниченного выполнения не выполняется.

```csharp
using System;
using System.Collections.Generic;
using System.Runtime.CompilerServices;

class Program
{
    static void Main(string[] args)
    {
        CallGenericMethods();
    }
    static void CallGenericMethods()
    {
        // This call is correct. The instantiation of the method
        // contains only nonreference types.
        MyClass.GenericMethodWithCer<int>();

        // This call is incorrect. A shared version of the method that
        // cannot be completely analyzed will be JIT-compiled. The 
        // MDA will be activated at JIT-compile time, not at run time.
        MyClass.GenericMethodWithCer<String>();
    }
}

class MyClass
{
    public static void GenericMethodWithCer<T>()
    {
        RuntimeHelpers.PrepareConstrainedRegions();
        try
        {

        }
        finally
        {
            // This is the start of the CER.
            Console.WriteLine("In finally block.");
        }
    }
}
```

## <a name="see-also"></a>См. также:

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
