---
title: notMarshalable MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 489f0e2ff4dc1eeaa9721ec6cf59faad0bee2ca8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="notmarshalable-mda"></a><span data-ttu-id="8395e-102">notMarshalable MDA</span><span class="sxs-lookup"><span data-stu-id="8395e-102">notMarshalable MDA</span></span>
<span data-ttu-id="8395e-103">Помощник по отладке (MDA) управляемого кода `notMarshalable` активируется, когда среда CLR обнаруживает указатель интерфейса СОМ без допустимого зарегистрированного прокси или заглушки или неправильную реализацию интерфейса `IMarshal` при попытке выполнить маршалинг интерфейса по контекстам.</span><span class="sxs-lookup"><span data-stu-id="8395e-103">The `notMarshalable` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters a COM interface pointer without a valid registered proxy/stub or an incorrect `IMarshal` interface implementation while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8395e-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="8395e-104">Symptoms</span></span>  
 <span data-ttu-id="8395e-105">Вызовы не обслуживаются, или вызовы выполняются из неправильного контекста для указателей интерфейса СОМ.</span><span class="sxs-lookup"><span data-stu-id="8395e-105">Calls are not serviced, or calls occur in the wrong context for COM interface pointers.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8395e-106">Причина</span><span class="sxs-lookup"><span data-stu-id="8395e-106">Cause</span></span>  
 <span data-ttu-id="8395e-107">Отсутствует допустимый зарегистрированный прокси или заглушка, или неправильный `IMarshal` при попытке выполнить маршалинг интерфейса по контекстам.</span><span class="sxs-lookup"><span data-stu-id="8395e-107">No valid registered proxy/stub or an incorrect `IMarshal` while attempting to marshal the interface across contexts.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8395e-108">Решение</span><span class="sxs-lookup"><span data-stu-id="8395e-108">Resolution</span></span>  
 <span data-ttu-id="8395e-109">Убедитесь, что имеются зарегистрированный прокси или заглушка и что реализация `IMarshal` является допустимой.</span><span class="sxs-lookup"><span data-stu-id="8395e-109">Make sure you have a proxy stub registered and that the `IMarshal` implementation is valid.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8395e-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="8395e-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="8395e-111">Этот MDA не оказывает никакого влияния на среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="8395e-111">This MDA has no effect on the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8395e-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="8395e-112">Output</span></span>  
 <span data-ttu-id="8395e-113">Сообщение, описывающее проблему.</span><span class="sxs-lookup"><span data-stu-id="8395e-113">A message describing the problem.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8395e-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="8395e-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8395e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8395e-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="8395e-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="8395e-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="8395e-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="8395e-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
