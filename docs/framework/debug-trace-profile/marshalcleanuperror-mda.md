---
title: marshalCleanupError MDA
ms.date: 03/30/2017
helpviewer_keywords:
- cleanup operations
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- marshaling cleanup error
- MarshalCleanupError MDA
- memory, cleanup errors
ms.assetid: 2f5d9e7c-ae51-4155-a435-54347aa1f091
ms.openlocfilehash: 1a14c548ce960d53f47934595171189db28edfbb
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216159"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="ed7d3-102">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="ed7d3-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="ed7d3-103">Помощник отладки управляемого кода (MDA) `marshalCleanupError` активируется, когда при попытке очистить временные структуры и память, используемые для маршалинга типов данных между границами машинного и управляемого кода, в среде CLR возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ed7d3-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ed7d3-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="ed7d3-104">Symptoms</span></span>  
 <span data-ttu-id="ed7d3-105">При переходах между машинным и управляемым кодом возникает утечка памяти, не восстанавливается состояние среды, например культура потока, либо возникают ошибки при очистке <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="ed7d3-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ed7d3-106">Причина</span><span class="sxs-lookup"><span data-stu-id="ed7d3-106">Cause</span></span>  
 <span data-ttu-id="ed7d3-107">Во время очистки временных структур возникла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ed7d3-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ed7d3-108">Решение</span><span class="sxs-lookup"><span data-stu-id="ed7d3-108">Resolution</span></span>  
 <span data-ttu-id="ed7d3-109">Проверьте все реализации деструктора <xref:System.Runtime.InteropServices.SafeHandle>, метода завершения и особого упаковщика на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="ed7d3-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ed7d3-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="ed7d3-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="ed7d3-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="ed7d3-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ed7d3-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="ed7d3-112">Output</span></span>  
 <span data-ttu-id="ed7d3-113">Сообщение с указанием операции, завершившейся со сбоем во время очистки.</span><span class="sxs-lookup"><span data-stu-id="ed7d3-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ed7d3-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="ed7d3-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed7d3-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="ed7d3-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="ed7d3-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="ed7d3-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ed7d3-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ed7d3-117">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
