---
title: Помощник по отладке управляемого кода invalidCERCall
ms.date: 03/30/2017
helpviewer_keywords:
- invalid CER calls
- InvalidCERCall MDA
- MDAs (managed debugging assistants), CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: c4577410-602e-44e5-9dab-fea7c55bcdfe
ms.openlocfilehash: f8e467401f7c50898613c7cf6eca68a8a705431a
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217384"
---
# <a name="invalidcercall-mda"></a>Помощник по отладке управляемого кода invalidCERCall
Помощник по отладке управляемого кода (MDA) `invalidCERCall` активируется при осуществляемом в графе области ограниченного исполнения (CER) вызове метода, не имеющего контракта надежности или имеющего чрезвычайно слабый контракт. Слабый контракт представляет собой контракт, который объявляет, что максимальное повреждение состояния имеет большую область, чем экземпляр, переданный в вызов, то есть <xref:System.AppDomain> или состояние процесса может быть повреждено или его результат не всегда является детерминированно вычисляемым при вызове в рамках CER.  
  
## <a name="symptoms"></a>Симптомы  
 Неожиданные результаты при выполнении кода в CER. Признаки не являются специфическими. Это могут быть непредвиденные <xref:System.OutOfMemoryException>, <xref:System.Threading.ThreadAbortException> или другие исключения при вызове ненадежного метода, так как среда выполнения не подготовила его заранее или не защитила его от исключений <xref:System.Threading.ThreadAbortException> во время выполнения. Гораздо более серьезной угрозой является то, что любое исключение, возникающие в методе во время выполнения, может оставить <xref:System.AppDomain> или процесс в нестабильном состоянии, что противоречит цели CER. Причина, по которой создается CER, — необходимость избегать подобных повреждений состояния. Признаки поврежденного состояния связаны с конкретным приложением из-за различий определения согласованного состояния между приложениями.  
  
## <a name="cause"></a>Причина  
 Код внутри CER вызывает функцию без <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute> или со слабым <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute>, который несовместим с работающими в CER.  
  
 С точки зрения синтаксиса контракта надежности, слабый контракт — это контракт, который не указывает значение перечисления <xref:System.Runtime.ConstrainedExecution.Consistency> или указывает значение <xref:System.Runtime.ConstrainedExecution.Consistency> для <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptProcess>, <xref:System.Runtime.ConstrainedExecution.Consistency.MayCorruptAppDomain> или <xref:System.Runtime.ConstrainedExecution.Cer.None>. Любое из этих условий означает, что вызываемый код может отрицательно повлиять на попытки другого кода в CER поддерживать согласованное состояние.  Области CER позволяют коду обрабатывать ошибки детерминированным образом, сохраняя внутренние инварианты, которые важны для приложения, и позволяя ему продолжать выполнение в условиях возникновения временных ошибок, таких как исключения нехватки памяти.  
  
 Активация данного MDA указывает на возможность сбоя вызова метода в CER неожиданным для вызывающего объекта образом или таким образом, что происходит повреждение или неустранимая ошибка <xref:System.AppDomain> или состояния процесса. Конечно, вызываемый код может выполняться правильно, а проблема заключается просто в отсутствии контракта. Однако проблемы, связанные с написанием надежного кода, несущественны, и отсутствие контракта является хорошим показателем вероятности неправильного выполнения кода. Контракты — это показатели написания надежного кода, а также гарантия сохранения этой надежности при будущих правках кода.  Иными словами, контракты являются заявлениями о намерениях, а не только выражают детали реализации.  
  
 Поскольку любой метод со слабым или несуществующим контрактом может привести к сбою целым рядом неожиданных способов, среда выполнения не пытается удалить собственные непредсказуемые сбои из метода, представленные, например, отложенной JIT-компиляцией, заполнением словаря универсальных типов или прерываниями потоков. То есть когда данный MDA активируется, он указывает, что среда выполнения не включила вызываемый метода в определенную область CER. Граф вызовов был прерван на этом узле, поскольку дальнейшая подготовка этого поддерева поможет скрыть потенциальную ошибку.  
  
## <a name="resolution"></a>Решение  
 Добавьте в функцию допустимый контракт надежности или избегайте использовать этот вызов функции.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 В результате вызова слабого контракта из CER может произойти сбой при завершении работы. Это может привести к повреждению состояния процесса <xref:System.AppDomain>.  
  
## <a name="output"></a>Вывод  
 Ниже представлен пример выходных данных этого MDA.  
  
 `Method 'MethodWithCer', while executing within a constrained execution region, makes a call at IL offset 0x000C to 'MethodWithWeakContract', which does not have a sufficiently strong reliability contract and might cause non-deterministic results.`  
  
## <a name="configuration"></a>Конфигурация  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>
- <xref:System.Runtime.ConstrainedExecution>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](diagnosing-errors-with-managed-debugging-assistants.md)
