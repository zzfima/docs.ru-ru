---
title: invalidGCHandleCookie MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), invalid cookies
- cookies, invalid
- managed debugging assistants (MDAs), invalid cookies
- InvalidGCHandleCookie MDA
- invalid cookies
ms.assetid: 613ad742-3c11-401d-a6b3-893ceb8de4f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 876f0fe3c40cb6754b4ba714833dd160dc4de3a8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59176960"
---
# <a name="invalidgchandlecookie-mda"></a><span data-ttu-id="ef37d-102">invalidGCHandleCookie MDA</span><span class="sxs-lookup"><span data-stu-id="ef37d-102">invalidGCHandleCookie MDA</span></span>
<span data-ttu-id="ef37d-103">Помощник по отладке управляемого кода (MDA) `invalidGCHandleCookie` активируется при попытке преобразования из недопустимого файла cookie <xref:System.IntPtr> в <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="ef37d-103">The `invalidGCHandleCookie` managed debugging assistant (MDA) is activated when a conversion from an invalid <xref:System.IntPtr> cookie to a <xref:System.Runtime.InteropServices.GCHandle> is attempted.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ef37d-104">Симптомы</span><span class="sxs-lookup"><span data-stu-id="ef37d-104">Symptoms</span></span>  
 <span data-ttu-id="ef37d-105">Неопределенное поведение, например нарушения прав доступа и повреждение памяти, при попытке использовать или получить <xref:System.Runtime.InteropServices.GCHandle> из <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="ef37d-105">Undefined behavior such as access violations and memory corruption while attempting to use or retrieve a <xref:System.Runtime.InteropServices.GCHandle> from an <xref:System.IntPtr>.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ef37d-106">Причина</span><span class="sxs-lookup"><span data-stu-id="ef37d-106">Cause</span></span>  
 <span data-ttu-id="ef37d-107">Возможно, файл cookie является недопустимым, так как он не был изначально создан из <xref:System.Runtime.InteropServices.GCHandle>, представляет <xref:System.Runtime.InteropServices.GCHandle>, который уже был освобожден, является файлом cookie для <xref:System.Runtime.InteropServices.GCHandle> в другом домене приложения или был упакован в собственный код как <xref:System.Runtime.InteropServices.GCHandle>, но передан обратно в среду CLR в качестве <xref:System.IntPtr>, где была выполнена попытка приведения к типу.</span><span class="sxs-lookup"><span data-stu-id="ef37d-107">The cookie is probably invalid because it was not originally created from a <xref:System.Runtime.InteropServices.GCHandle>, represents a <xref:System.Runtime.InteropServices.GCHandle> that has already been freed, is a cookie to a <xref:System.Runtime.InteropServices.GCHandle> in a different application domain, or was marshaled to native code as a <xref:System.Runtime.InteropServices.GCHandle> but passed back into the CLR as an <xref:System.IntPtr>, where a cast was attempted.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ef37d-108">Решение</span><span class="sxs-lookup"><span data-stu-id="ef37d-108">Resolution</span></span>  
 <span data-ttu-id="ef37d-109">Укажите допустимый файл cookie <xref:System.IntPtr> для <xref:System.Runtime.InteropServices.GCHandle>.</span><span class="sxs-lookup"><span data-stu-id="ef37d-109">Specify a valid <xref:System.IntPtr> cookie for the <xref:System.Runtime.InteropServices.GCHandle>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ef37d-110">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="ef37d-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="ef37d-111">Если этот MDA включен, отладчик больше не может отслеживать корни обратно в их объекты, поскольку значения файла cookie, переданные обратно, отличаются от значений, возвращаемых при отключенном MDA.</span><span class="sxs-lookup"><span data-stu-id="ef37d-111">When this MDA is enabled, the debugger is no longer able to trace the roots back to their objects because the cookie values passed back are different from the ones returned when the MDA is not enabled.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ef37d-112">Вывод</span><span class="sxs-lookup"><span data-stu-id="ef37d-112">Output</span></span>  
 <span data-ttu-id="ef37d-113">Указывается значение недопустимого файла cookie <xref:System.IntPtr>.</span><span class="sxs-lookup"><span data-stu-id="ef37d-113">The invalid <xref:System.IntPtr> cookie value is reported.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ef37d-114">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="ef37d-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidGCHandleCookie />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef37d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ef37d-115">See also</span></span>

- <xref:System.Runtime.InteropServices.GCHandle.FromIntPtr%2A>
- <xref:System.Runtime.InteropServices.GCHandle>
- [<span data-ttu-id="ef37d-116">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="ef37d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
