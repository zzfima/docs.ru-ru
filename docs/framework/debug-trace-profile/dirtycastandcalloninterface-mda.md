---
title: Помощник по отладке управляемого кода dirtyCastAndCallOnInterface
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a28820479ca15ad72475ae9a7754bbbf99ce5c5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754717"
---
# <a name="dirtycastandcalloninterface-mda"></a>Помощник по отладке управляемого кода dirtyCastAndCallOnInterface
Помощник по отладке управляемого кода (MDA) `dirtyCastAndCallOnInterface` активируется при попытке выполнения вызова с ранним связыванием посредством виртуальной таблицы в интерфейсе класса, который был отмечен как интерфейс только позднего связывания.  
  
## <a name="symptoms"></a>Симптомы  
 Приложение вызывает нарушение прав доступа или проявляет непредвиденное поведение при размещении вызова с ранним связыванием посредством СОМ в среде CLR.  
  
## <a name="cause"></a>Причина  
 Код пытается выполнить вызов с ранним связыванием с помощью виртуальной таблицы через интерфейс класса, отмеченный как интерфейс только позднего связывания. Обратите внимание, что по умолчанию интерфейсы класса определяются как интерфейсы только позднего связывания. Они также могут быть идентифицированы как интерфейсы позднего связывания с помощью атрибута <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> со значением <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).  
  
## <a name="resolution"></a>Решение  
 Рекомендуемое решение состоит в определении явного интерфейса для использования в COM и выполнении вызова клиентов COM через этот интерфейс вместо автоматически созданного интерфейса класса. Кроме того, вызов из COM можно преобразовать в вызов с поздним связыванием посредством `IDispatch`.  
  
 Наконец, возможно идентифицировать класс как <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`), чтобы разрешить размещение вызовов с ранним связыванием из COM; однако использование <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> категорически не рекомендуется из-за ограничений управления версиями, описанных в <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.  
  
## <a name="effect-on-the-runtime"></a>Влияние на среду выполнения  
 Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR. Он только сообщает данные о вызовах с ранним связыванием в интерфейсах позднего связывания.  
  
## <a name="output"></a>Вывод  
 Имя метода или имя поля, доступного для вызова с ранним связыванием.  
  
## <a name="configuration"></a>Параметр Configuration  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [Диагностика ошибок посредством помощников по отладке управляемого кода](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
