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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2399f72b6efcdf69d8ff4bb3bce541073063c750
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096593"
---
# <a name="marshalcleanuperror-mda"></a><span data-ttu-id="933c8-102">marshalCleanupError MDA</span><span class="sxs-lookup"><span data-stu-id="933c8-102">marshalCleanupError MDA</span></span>
<span data-ttu-id="933c8-103">Помощник отладки управляемого кода (MDA) `marshalCleanupError` активируется, когда при попытке очистить временные структуры и память, используемые для маршалинга типов данных между границами машинного и управляемого кода, в среде CLR возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="933c8-103">The `marshalCleanupError` managed debugging assistant (MDA) is activated when the common language runtime (CLR) encounters an error while attempting to clean up temporary structures and memory used for marshaling data types between native and managed code boundaries.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="933c8-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="933c8-104">Symptoms</span></span>  
 <span data-ttu-id="933c8-105">При переходах между машинным и управляемым кодом возникает утечка памяти, не восстанавливается состояние среды, например культура потока, либо возникают ошибки при очистке <xref:System.Runtime.InteropServices.SafeHandle>.</span><span class="sxs-lookup"><span data-stu-id="933c8-105">A memory leak occurs when making native and managed code transitions, runtime state such as thread culture is not restored, or errors occur in <xref:System.Runtime.InteropServices.SafeHandle> cleanup.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="933c8-106">Причина</span><span class="sxs-lookup"><span data-stu-id="933c8-106">Cause</span></span>  
 <span data-ttu-id="933c8-107">Во время очистки временных структур возникла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="933c8-107">An unexpected error occurred while cleaning up temporary structures.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="933c8-108">Решение</span><span class="sxs-lookup"><span data-stu-id="933c8-108">Resolution</span></span>  
 <span data-ttu-id="933c8-109">Проверьте все реализации деструктора <xref:System.Runtime.InteropServices.SafeHandle>, метода завершения и особого упаковщика на наличие ошибок.</span><span class="sxs-lookup"><span data-stu-id="933c8-109">Review all <xref:System.Runtime.InteropServices.SafeHandle> destructor, finalizer, and custom marshaler implementations for errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="933c8-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="933c8-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="933c8-111">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="933c8-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="933c8-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="933c8-112">Output</span></span>  
 <span data-ttu-id="933c8-113">Сообщение с указанием операции, завершившейся со сбоем во время очистки.</span><span class="sxs-lookup"><span data-stu-id="933c8-113">A message reporting the operation that failed during cleanup.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="933c8-114">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="933c8-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshalCleanupError />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="933c8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="933c8-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="933c8-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="933c8-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="933c8-117">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="933c8-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
