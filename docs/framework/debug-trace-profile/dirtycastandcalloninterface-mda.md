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
ms.openlocfilehash: 6e4f0074958e8a6a8ca322968e9c29e89481c0c8
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216519"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="7cfe9-102">Помощник по отладке управляемого кода dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="7cfe9-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="7cfe9-103">Помощник по отладке управляемого кода (MDA) `dirtyCastAndCallOnInterface` активируется при попытке выполнения вызова с ранним связыванием посредством виртуальной таблицы в интерфейсе класса, который был отмечен как интерфейс только позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="7cfe9-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="7cfe9-104">Symptoms</span></span>  
 <span data-ttu-id="7cfe9-105">Приложение вызывает нарушение прав доступа или проявляет непредвиденное поведение при размещении вызова с ранним связыванием посредством СОМ в среде CLR.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="7cfe9-106">Причина</span><span class="sxs-lookup"><span data-stu-id="7cfe9-106">Cause</span></span>  
 <span data-ttu-id="7cfe9-107">Код пытается выполнить вызов с ранним связыванием с помощью виртуальной таблицы через интерфейс класса, отмеченный как интерфейс только позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="7cfe9-108">Обратите внимание, что по умолчанию интерфейсы класса определяются как интерфейсы только позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="7cfe9-109">Они также могут быть идентифицированы как интерфейсы позднего связывания с помощью атрибута <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> со значением <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span><span class="sxs-lookup"><span data-stu-id="7cfe9-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="7cfe9-110">Решение</span><span class="sxs-lookup"><span data-stu-id="7cfe9-110">Resolution</span></span>  
 <span data-ttu-id="7cfe9-111">Рекомендуемое решение состоит в определении явного интерфейса для использования в COM и выполнении вызова клиентов COM через этот интерфейс вместо автоматически созданного интерфейса класса.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="7cfe9-112">Кроме того, вызов из COM можно преобразовать в вызов с поздним связыванием посредством `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="7cfe9-113">Наконец, возможно идентифицировать класс как <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`), чтобы разрешить размещение вызовов с ранним связыванием из COM; однако использование <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> категорически не рекомендуется из-за ограничений управления версиями, описанных в <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="7cfe9-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="7cfe9-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="7cfe9-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="7cfe9-116">Он только сообщает данные о вызовах с ранним связыванием в интерфейсах позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="7cfe9-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="7cfe9-117">Output</span></span>  
 <span data-ttu-id="7cfe9-118">Имя метода или имя поля, доступного для вызова с ранним связыванием.</span><span class="sxs-lookup"><span data-stu-id="7cfe9-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="7cfe9-119">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="7cfe9-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cfe9-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="7cfe9-120">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="7cfe9-121">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="7cfe9-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
