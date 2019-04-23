---
title: invalidOverlappedToPinvoke MDA
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4bdb2035906b9383342201017b58d1d0050113b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084561"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="1fb02-102">invalidOverlappedToPinvoke MDA</span><span class="sxs-lookup"><span data-stu-id="1fb02-102">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="1fb02-103">Помощник по отладке управляемого кода (MDA) `invalidOverlappedToPinvoke` активируется, когда перекрытый указатель, который не был создан в куче сбора мусора, передается конкретным функциям Win32.</span><span class="sxs-lookup"><span data-stu-id="1fb02-103">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1fb02-104">По умолчанию данный MDA активируется, только если в коде определен платформенный вызов, и отладчик сообщает о статусе JustMyCode для каждого метода.</span><span class="sxs-lookup"><span data-stu-id="1fb02-104">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="1fb02-105">Отладчик, который не понимает JustMyCode (например, MDbg.exe без расширений), не будет активировать данный MDA.</span><span class="sxs-lookup"><span data-stu-id="1fb02-105">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="1fb02-106">Этот MDA можно включить для таких отладчиков с помощью файла конфигурации и явно задав `justMyCode="false"` в файле .mda.config `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`.</span><span class="sxs-lookup"><span data-stu-id="1fb02-106">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="1fb02-107">Симптомы</span><span class="sxs-lookup"><span data-stu-id="1fb02-107">Symptoms</span></span>  
 <span data-ttu-id="1fb02-108">Сбои или необъяснимые повреждения кучи.</span><span class="sxs-lookup"><span data-stu-id="1fb02-108">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="1fb02-109">Причина</span><span class="sxs-lookup"><span data-stu-id="1fb02-109">Cause</span></span>  
 <span data-ttu-id="1fb02-110">Перекрытый указатель, который не был создан в куче сборки мусора, передается конкретным функциям операционной системы.</span><span class="sxs-lookup"><span data-stu-id="1fb02-110">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="1fb02-111">В следующей таблице приведены функции, отслеживаемые данным MDA.</span><span class="sxs-lookup"><span data-stu-id="1fb02-111">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="1fb02-112">Module</span><span class="sxs-lookup"><span data-stu-id="1fb02-112">Module</span></span>|<span data-ttu-id="1fb02-113">Функция</span><span class="sxs-lookup"><span data-stu-id="1fb02-113">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="1fb02-114">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-114">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="1fb02-115">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-115">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="1fb02-116">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-116">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="1fb02-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-117">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="1fb02-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-118">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="1fb02-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-119">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="1fb02-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-120">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="1fb02-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-121">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="1fb02-122">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-122">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="1fb02-123">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-123">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="1fb02-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-124">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="1fb02-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-125">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="1fb02-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-126">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="1fb02-127">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="1fb02-127">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="1fb02-128">Для этого условия велика вероятность повреждения кучи, так как делающий вызов <xref:System.AppDomain> может быть выгружен.</span><span class="sxs-lookup"><span data-stu-id="1fb02-128">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="1fb02-129">В случае выгрузки <xref:System.AppDomain> код приложения либо освободит память для перекрытого указателя, что приведет к повреждению при завершении операции, либо произойдет утечка памяти, что приведет к проблемам в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="1fb02-129">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="1fb02-130">Решение</span><span class="sxs-lookup"><span data-stu-id="1fb02-130">Resolution</span></span>  
 <span data-ttu-id="1fb02-131">Используйте объект <xref:System.Threading.Overlapped>, вызвав метод <xref:System.Threading.Overlapped.Pack%2A> для получения структуры <xref:System.Threading.NativeOverlapped>, которую можно передать в функцию.</span><span class="sxs-lookup"><span data-stu-id="1fb02-131">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="1fb02-132">В случае выгрузки <xref:System.AppDomain> среда CLR ожидает завершения асинхронной операции, прежде чем освободить указатель.</span><span class="sxs-lookup"><span data-stu-id="1fb02-132">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1fb02-133">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="1fb02-133">Effect on the Runtime</span></span>  
 <span data-ttu-id="1fb02-134">Этот помощник отладки управляемого кода не оказывал никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="1fb02-134">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1fb02-135">Вывод</span><span class="sxs-lookup"><span data-stu-id="1fb02-135">Output</span></span>  
 <span data-ttu-id="1fb02-136">Ниже представлен пример выходных данных этого MDA.</span><span class="sxs-lookup"><span data-stu-id="1fb02-136">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="1fb02-137">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="1fb02-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1fb02-138">См. также</span><span class="sxs-lookup"><span data-stu-id="1fb02-138">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="1fb02-139">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="1fb02-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="1fb02-140">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="1fb02-140">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
