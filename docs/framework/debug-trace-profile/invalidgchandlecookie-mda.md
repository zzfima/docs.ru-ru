---
title: invalidGCHandleCookie MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f4cb7655d8d70cf46926cf193d6594523316e81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="d1d23-102">invalidGCHandleCookie MDA</span><span class="sxs-lookup"><span data-stu-id="d1d23-102">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="d1d23-103">Помощник по отладке управляемого кода (MDA) `invalidGCHandleCookie` активируется при попытке преобразования из недопустимого файла cookie <xref:System.IntPtr> в <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="d1d23-103">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d1d23-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="d1d23-104">Symptoms</span></span>  
 <span data-ttu-id="d1d23-105">Неопределенное поведение, например нарушения прав доступа и повреждение памяти, при попытке использовать или получить <xref:System.Runtime.InteropServices.GCHandle> из <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="d1d23-105">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d1d23-106">Причина</span><span class="sxs-lookup"><span data-stu-id="d1d23-106">Cause</span></span>  
 <span data-ttu-id="d1d23-107">Возможно, файл cookie является недопустимым, так как он не был изначально создан из <xref:System.Runtime.InteropServices.GCHandle>, представляет <xref:System.Runtime.InteropServices.GCHandle>, который уже был освобожден, является файлом cookie для <xref:System.Runtime.InteropServices.GCHandle> в другом домене приложения или был упакован в собственный код как <xref:System.Runtime.InteropServices.GCHandle>, но передан обратно в среду CLR в качестве <xref:System.IntPtr>, где была выполнена попытка приведения к типу.</span><span class="sxs-lookup"><span data-stu-id="d1d23-107">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d1d23-108">Решение</span><span class="sxs-lookup"><span data-stu-id="d1d23-108">Resolution</span></span>  
 <span data-ttu-id="d1d23-109">Укажите допустимый файл cookie <xref:System.IntPtr> для <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="d1d23-109">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d1d23-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="d1d23-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="d1d23-111">Если этот MDA включен, отладчик больше не может отслеживать корни обратно в их объекты, поскольку значения файла cookie, переданные обратно, отличаются от значений, возвращаемых при отключенном MDA.</span><span class="sxs-lookup"><span data-stu-id="d1d23-111">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d1d23-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="d1d23-112">Output</span></span>  
 <span data-ttu-id="d1d23-113">Указывается значение недопустимого файла cookie <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="d1d23-113">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="d1d23-114">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="d1d23-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1d23-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d1d23-115">See Also</span></span>  
 <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>  
 <xref:System.Runtime.InteropServices.GCHandle>  
 [<span data-ttu-id="d1d23-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="d1d23-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
