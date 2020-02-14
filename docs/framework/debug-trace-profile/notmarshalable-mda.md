---
title: notMarshalable MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
ms.openlocfilehash: 45db0e70b2446fa6e3175409bcc3844042f0acc0
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217283"
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="f861d-102">notMarshalable MDA</span><span class="sxs-lookup"><span data-stu-id="f861d-102">notMarshalable MDA</span></span>
<span data-ttu-id="f861d-103">Помощник по отладке (MDA) управляемого кода `notMarshalable` активируется, когда среда CLR обнаруживает указатель интерфейса СОМ без допустимого зарегистрированного прокси или заглушки или неправильную реализацию интерфейса `IMarshal` при попытке выполнить маршалинг интерфейса по контекстам.</span><span class="sxs-lookup"><span data-stu-id="f861d-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f861d-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="f861d-104">Symptoms</span></span>  
 <span data-ttu-id="f861d-105">Вызовы не обслуживаются, или вызовы выполняются из неправильного контекста для указателей интерфейса СОМ.</span><span class="sxs-lookup"><span data-stu-id="f861d-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f861d-106">Причина</span><span class="sxs-lookup"><span data-stu-id="f861d-106">Cause</span></span>  
 <span data-ttu-id="f861d-107">Отсутствует допустимый зарегистрированный прокси или заглушка, или неправильный `IMarshal` при попытке выполнить маршалинг интерфейса по контекстам.</span><span class="sxs-lookup"><span data-stu-id="f861d-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f861d-108">Решение</span><span class="sxs-lookup"><span data-stu-id="f861d-108">Resolution</span></span>  
 <span data-ttu-id="f861d-109">Убедитесь, что имеются зарегистрированный прокси или заглушка и что реализация `IMarshal` является допустимой.</span><span class="sxs-lookup"><span data-stu-id="f861d-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f861d-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="f861d-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="f861d-111">Этот MDA не оказывает никакого влияния на среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="f861d-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f861d-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="f861d-112">Output</span></span>  
 <span data-ttu-id="f861d-113">Сообщение, описывающее проблему.</span><span class="sxs-lookup"><span data-stu-id="f861d-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="f861d-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f861d-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f861d-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="f861d-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f861d-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="f861d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f861d-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="f861d-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
