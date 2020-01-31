---
title: Отладка в Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 91f311818b615ea8f166bb3362ec52d39fcd0297
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790322"
---
# <a name="silverlight-debugging"></a><span data-ttu-id="afaba-102">Отладка в Silverlight</span><span class="sxs-lookup"><span data-stu-id="afaba-102">Silverlight Debugging</span></span>
<span data-ttu-id="afaba-103">В этом разделе описываются среда и интерфейсы, предоставляемые средой CLR для поддержки отладки приложений на основе Silverlight, работающих в ОС Windows или на платформе Macintosh.</span><span class="sxs-lookup"><span data-stu-id="afaba-103">The topics in this section describe the environment and interfaces that the common language runtime (CLR) provides to support debugging Silverlight-based applications that are running on the Windows operating system, or on the Macintosh platform.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="afaba-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="afaba-104">In This Section</span></span>  
 [<span data-ttu-id="afaba-105">Функция EnumerateCLRs</span><span class="sxs-lookup"><span data-stu-id="afaba-105">EnumerateCLRs Function</span></span>](enumerateclrs-function.md)  
 <span data-ttu-id="afaba-106">Предоставляет механизм для перечисления сред CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="afaba-106">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
 [<span data-ttu-id="afaba-107">Функция CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="afaba-107">CloseCLREnumeration Function</span></span>](closeclrenumeration-function.md)  
 <span data-ttu-id="afaba-108">Закрывает все допустимые события продолжения запуска среды CLR, расположенные в массиве дескрипторов, возвращенных [функцией EnumerateCLRs](enumerateclrs-function.md), и освобождает память для массивов дескрипторов и строк.</span><span class="sxs-lookup"><span data-stu-id="afaba-108">Closes any valid CLR continue-startup events located in an array of handles returned by the [EnumerateCLRs Function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
 [<span data-ttu-id="afaba-109">Функция CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="afaba-109">CreateCoreClrDebugTarget Function</span></span>](createcoreclrdebugtarget-function.md)  
 <span data-ttu-id="afaba-110">Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="afaba-110">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="afaba-111">Функция CreateCordbObject</span><span class="sxs-lookup"><span data-stu-id="afaba-111">CreateCordbObject Function</span></span>](createcordbobject-function.md)  
 <span data-ttu-id="afaba-112">Создает интерфейс отладчика, обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.</span><span class="sxs-lookup"><span data-stu-id="afaba-112">Creates a debugger interface that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
 [<span data-ttu-id="afaba-113">Функция CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="afaba-113">CreateVersionStringFromModule Function</span></span>](createversionstringfrommodule-function.md)  
 <span data-ttu-id="afaba-114">Создает строку версии из пути среды CLR в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="afaba-114">Creates a version string from a CLR path in a target process.</span></span>  
  
 [<span data-ttu-id="afaba-115">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="afaba-115">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function-for-silverlight.md)  
 <span data-ttu-id="afaba-116">Принимает строку версии среды CLR, возвращаемую функцией [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md), и возвращает соответствующий интерфейс отладчика.</span><span class="sxs-lookup"><span data-stu-id="afaba-116">Accepts a CLR version string returned from [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md)function, and returns a corresponding debugger interface.</span></span>  
  
 [<span data-ttu-id="afaba-117">Структура CoreClrDebugProcInfo</span><span class="sxs-lookup"><span data-stu-id="afaba-117">CoreClrDebugProcInfo Structure</span></span>](coreclrdebugprocinfo-structure.md)  
 <span data-ttu-id="afaba-118">Представляет процесс, который выполняется на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="afaba-118">Represents a process that is running on a remote machine.</span></span>  
  
 [<span data-ttu-id="afaba-119">Структура CoreClrDebugRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="afaba-119">CoreClrDebugRuntimeInfo Structure</span></span>](coreclrdebugruntimeinfo-structure.md)  
 <span data-ttu-id="afaba-120">Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="afaba-120">Represents a CLR instance that is loaded in a process on a remote machine.</span></span>  
  
 [<span data-ttu-id="afaba-121">Функция GetStartupNotificationEvent</span><span class="sxs-lookup"><span data-stu-id="afaba-121">GetStartupNotificationEvent Function</span></span>](getstartupnotificationevent-function.md)  
 <span data-ttu-id="afaba-122">Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="afaba-122">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
 [<span data-ttu-id="afaba-123">Интерфейс ICoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="afaba-123">ICoreClrDebugTarget Interface</span></span>](icoreclrdebugtarget-interface.md)  
 <span data-ttu-id="afaba-124">Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="afaba-124">Creates a connection to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="afaba-125">Функция InitDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="afaba-125">InitDbgTransportManager Function</span></span>](initdbgtransportmanager-function.md)  
 <span data-ttu-id="afaba-126">Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="afaba-126">Initializes the transport manager to connect to a remote target for process and runtime enumeration.</span></span>  
  
 [<span data-ttu-id="afaba-127">Функция ShutdownDbgTransportManager</span><span class="sxs-lookup"><span data-stu-id="afaba-127">ShutdownDbgTransportManager Function</span></span>](shutdowndbgtransportmanager-function.md)  
 <span data-ttu-id="afaba-128">Завершает работу диспетчера транспорта для подключения к удаленному целевому компьютеру.</span><span class="sxs-lookup"><span data-stu-id="afaba-128">Shuts down the transport manager for a connection to a remote target machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afaba-129">См. также:</span><span class="sxs-lookup"><span data-stu-id="afaba-129">See also</span></span>

- [<span data-ttu-id="afaba-130">Коклассы отладки</span><span class="sxs-lookup"><span data-stu-id="afaba-130">Debugging Coclasses</span></span>](debugging-coclasses.md)
- [<span data-ttu-id="afaba-131">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="afaba-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="afaba-132">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="afaba-132">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
- [<span data-ttu-id="afaba-133">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="afaba-133">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="afaba-134">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="afaba-134">Debugging Structures</span></span>](debugging-structures.md)
