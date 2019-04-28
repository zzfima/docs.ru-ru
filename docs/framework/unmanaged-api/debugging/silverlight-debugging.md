---
title: Отладка в Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d20bc002e52c3c6a42b45c0d1c5d559e65dc52c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763667"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="79329-102">Отладка в Silverlight</span><span class="sxs-lookup"><span data-stu-id="79329-102">Silverlight Debugging</span></span>
<span data-ttu-id="79329-103">В этом разделе описываются среда и интерфейсы, предоставляемые средой CLR для поддержки отладки приложений на основе Silverlight, работающих в ОС Windows или на платформе Macintosh.</span><span class="sxs-lookup"><span data-stu-id="79329-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79329-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="79329-104">In This Section</span></span>  
 [<span data-ttu-id="79329-105">Функция EnumerateCLRs</span><span class="sxs-lookup"><span data-stu-id="79329-105">EnumerateCLRs Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)  
 <span data-ttu-id="79329-106">Предоставляет механизм для перечисления сред CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="79329-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="79329-107">Функция CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="79329-107">CloseCLREnumeration Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md)  
 <span data-ttu-id="79329-108">Закрывает все допустимые события продолжения запуска среды CLR, находятся в массиве дескрипторов, возвращенном [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)и освобождает память для массивов дескрипторов и строк пути.</span><span class="sxs-lookup"><span data-stu-id="79329-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="79329-109">Функция CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="79329-109">CreateCoreClrDebugTarget Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="79329-110">Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="79329-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="79329-111">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="79329-111">CreateCordbObject Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createcordbobject-function.md)  
 <span data-ttu-id="79329-112">Создает интерфейс отладчика, обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="79329-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="79329-113">Функция CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="79329-113">CreateVersionStringFromModule Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)  
 <span data-ttu-id="79329-114">Создает строку версии из пути среды CLR в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="79329-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="79329-115">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="79329-115">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="79329-116">Принимает строку версии среды CLR возвращаемые [функция CreateVersionStringFromModule](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)и возвращает соответствующий интерфейс отладчика.</span><span class="sxs-lookup"><span data-stu-id="79329-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](../../../../docs/framework/unmanaged-api/debugging/createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="79329-117">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="79329-117">CoreClrDebugProcInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="79329-118">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="79329-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="79329-119">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="79329-119">CoreClrDebugRuntimeInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="79329-120">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="79329-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="79329-121">Функция GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="79329-121">GetStartupNotificationEvent Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/getstartupnotificationevent-function.md)  
 <span data-ttu-id="79329-122">Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="79329-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="79329-123">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="79329-123">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="79329-124">Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="79329-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="79329-125">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="79329-125">InitDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/initdbgtransportmanager-function.md)  
 <span data-ttu-id="79329-126">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="79329-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="79329-127">Функция ShutdownDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="79329-127">ShutdownDbgTransportManager Function</span></span>](../../../../docs/framework/unmanaged-api/debugging/shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="79329-128">Завершает работу диспетчера транспорта для подключения к удаленному целевому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="79329-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79329-129">См. также</span><span class="sxs-lookup"><span data-stu-id="79329-129">See also</span></span>

- [<span data-ttu-id="79329-130">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="79329-130">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)
- [<span data-ttu-id="79329-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="79329-131">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="79329-132">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="79329-132">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
- [<span data-ttu-id="79329-133">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="79329-133">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="79329-134">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="79329-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
