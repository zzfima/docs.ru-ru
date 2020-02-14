---
title: disconnectedContext MDA
ms.date: 03/30/2017
helpviewer_keywords:
- DisconnectedContext MDA
- MDAs (managed debugging assistants), disconnected context
- dead context
- transitioning disconnected apartment or context
- context disconnections
- managed debugging assistants (MDAs), disconnected context
ms.assetid: 1887d31d-7006-4491-93b3-68fd5b05f71d
ms.openlocfilehash: 3d04e304a6b30fe6fd4deeda5a97007f11ee7b13
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216546"
---
# <a name="disconnectedcontext-mda"></a><span data-ttu-id="eb801-102">disconnectedContext MDA</span><span class="sxs-lookup"><span data-stu-id="eb801-102">disconnectedContext MDA</span></span>
<span data-ttu-id="eb801-103">Помощник отладки управляемого кода `disconnectedContext` (MDA) активируется, когда среда CLR пытается перейти в отключенное подразделение или контекст во время обслуживания запроса, связанного с COM-объектом.</span><span class="sxs-lookup"><span data-stu-id="eb801-103">The `disconnectedContext` managed debugging assistant (MDA) is activated when the CLR attempts to transition into a disconnected apartment or context while servicing a request concerning a COM object.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="eb801-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="eb801-104">Symptoms</span></span>  
 <span data-ttu-id="eb801-105">Вызовы, выполняемые для [вызываемой оболочки времени выполнения](../../standard/native-interop/runtime-callable-wrapper.md) (RCW), направляются в базовый компонент COM в текущем подразделении или контексте вместо того, где они существуют.</span><span class="sxs-lookup"><span data-stu-id="eb801-105">Calls made on a [Runtime Callable Wrapper](../../standard/native-interop/runtime-callable-wrapper.md) (RCW) are delivered to the underlying COM component in the current apartment or context instead of the one in which they exist.</span></span> <span data-ttu-id="eb801-106">Это может привести к повреждению или потере данных, если компонент COM не является многопоточным, как в случае с компонентами однопотокового подразделения (STA).</span><span class="sxs-lookup"><span data-stu-id="eb801-106">This can cause corruption and or data loss if the COM component is not multithreaded, as in the case of single-threaded apartment (STA) components.</span></span> <span data-ttu-id="eb801-107">Кроме того, если сама вызываемая оболочка времени выполнения является прокси-сервером, вызов может привести к возникновению исключения <xref:System.Runtime.InteropServices.COMException> с HRESULT RPC_E_WRONG_THREAD.</span><span class="sxs-lookup"><span data-stu-id="eb801-107">Alternatively, if the RCW is itself a proxy, the call might result in the throwing of a <xref:System.Runtime.InteropServices.COMException> with an HRESULT of RPC_E_WRONG_THREAD.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="eb801-108">Причина</span><span class="sxs-lookup"><span data-stu-id="eb801-108">Cause</span></span>  
 <span data-ttu-id="eb801-109">Работа контекста или подразделения OLE была завершена, когда среда CLR попыталась перейти в них.</span><span class="sxs-lookup"><span data-stu-id="eb801-109">The OLE apartment or context has been shut down when the CLR attempts to transition into it.</span></span> <span data-ttu-id="eb801-110">Чаще всего это вызвано завершением работы однопотоковых подразделений до полного освобождения всех компонентов COM, принадлежащих этому подразделению. Это может произойти в результате явного вызова из пользовательского кода в вызываемой оболочке времени выполнения либо во время работы среды CLR с этим компонентом COM, например, когда среда CLR освобождает компонент COM после сборки мусора для соответствующей вызываемой оболочки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="eb801-110">This is most commonly caused by STA apartments being shut down before all the COM components owned by the apartment were completely released This can occur as a result of an explicit call from user code on an RCW or while the CLR itself is manipulating the COM component, for example when the CLR is releasing the COM component when the associated RCW has been garbage collected.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="eb801-111">Решение</span><span class="sxs-lookup"><span data-stu-id="eb801-111">Resolution</span></span>  
 <span data-ttu-id="eb801-112">Чтобы избежать этой проблемы, убедитесь, что поток, которому принадлежит однопотоковое подразделение, не завершает работу до тех пор, пока приложение не завершит обработку всех объектов, находящихся в подразделении.</span><span class="sxs-lookup"><span data-stu-id="eb801-112">To avoid this problem, ensure the thread that owns the STA does not terminate before the application has finished with all the objects that live in the apartment.</span></span> <span data-ttu-id="eb801-113">То же самое касается и контекстов — убедитесь, что контексты не завершают работу до тех пор, пока приложение не завершит обработку всех COM-объектов, находящихся в этом контексте.</span><span class="sxs-lookup"><span data-stu-id="eb801-113">The same applies to contexts; ensure contexts are not shut down before the application is completely finished with any COM components that live inside the context.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="eb801-114">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="eb801-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="eb801-115">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="eb801-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="eb801-116">Он только выводит данные об отключенном контексте.</span><span class="sxs-lookup"><span data-stu-id="eb801-116">It only reports data about the disconnected context.</span></span>  
  
## <a name="output"></a><span data-ttu-id="eb801-117">Вывод</span><span class="sxs-lookup"><span data-stu-id="eb801-117">Output</span></span>  
 <span data-ttu-id="eb801-118">Указание файла cookie контекста для отключенного подразделения или контекста.</span><span class="sxs-lookup"><span data-stu-id="eb801-118">Reports the context cookie of the disconnected apartment or context.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="eb801-119">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="eb801-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <disconnectedContext />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb801-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="eb801-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="eb801-121">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="eb801-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="eb801-122">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="eb801-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
