---
title: Помощник по отладке управляемого кода failedQI
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: 4c36ec514645a38ef1228e76bdf6dbd06e886bae
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217503"
---
# <a name="failedqi-mda"></a><span data-ttu-id="b5797-102">Помощник по отладке управляемого кода failedQI</span><span class="sxs-lookup"><span data-stu-id="b5797-102">failedQI MDA</span></span>
<span data-ttu-id="b5797-103">Помощник по отладке управляемого кода (MDA) `failedQI` активируется, когда среда выполнения вызывает `QueryInterface`в указателе интерфейса СОМ от имени вызываемой оболочки времени выполнения (RCW), и вызов `QueryInterface` завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5797-103">The `failedQI` managed debugging assistant (MDA) is activated when the runtime calls `QueryInterface` on a COM interface pointer on behalf of a runtime callable wrapper (RCW), and the `QueryInterface` call fails.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b5797-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="b5797-104">Symptoms</span></span>  
 <span data-ttu-id="b5797-105">Произошел сбой приведения в RCW, или вызов COM из RCW неожиданно завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b5797-105">A cast on an RCW fails, or a call to COM from an RCW fails unexpectedly.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b5797-106">Причина</span><span class="sxs-lookup"><span data-stu-id="b5797-106">Cause</span></span>  
  
- <span data-ttu-id="b5797-107">Вызов выполняется из неправильного контекста.</span><span class="sxs-lookup"><span data-stu-id="b5797-107">The call is made from the wrong context.</span></span>  
  
- <span data-ttu-id="b5797-108">Зарегистрированному прокси-серверу не удается выполнить вызов `QueryInterface`, поскольку вызов выполнялся из неправильного контекста.</span><span class="sxs-lookup"><span data-stu-id="b5797-108">The registered proxy is failing the `QueryInterface` call because the call was attempted in the wrong context.</span></span>  
  
- <span data-ttu-id="b5797-109">Прокси-сервер, принадлежащий OLE, возвратил значение HRESULT, указывающее на сбой.</span><span class="sxs-lookup"><span data-stu-id="b5797-109">An OLE-owned proxy returned a failure HRESULT.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b5797-110">Решение</span><span class="sxs-lookup"><span data-stu-id="b5797-110">Resolution</span></span>  
 <span data-ttu-id="b5797-111">Правила COM см. в документации MSDN.</span><span class="sxs-lookup"><span data-stu-id="b5797-111">See the MSDN documentation on COM rules.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b5797-112">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="b5797-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="b5797-113">Если вызов `QueryInterface` завершается с ошибкой, контекст переключается и предпринимается попытка повторно выполнить вызов `QueryInterface`, чтобы увидеть, не использовался ли при сбое неправильный контекст.</span><span class="sxs-lookup"><span data-stu-id="b5797-113">If a `QueryInterface` call fails, the context is switched and the `QueryInterface` call is attempted again to see if an incorrect context was at fault.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b5797-114">Вывод</span><span class="sxs-lookup"><span data-stu-id="b5797-114">Output</span></span>  
 <span data-ttu-id="b5797-115">Управляемое имя интерфейса, идентификатор GUID интерфейса и значение HRESULT ошибки.</span><span class="sxs-lookup"><span data-stu-id="b5797-115">The managed name of the interface, the GUID of the interface, and the HRESULT of the failure.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b5797-116">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="b5797-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5797-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5797-117">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b5797-118">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="b5797-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b5797-119">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="b5797-119">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
