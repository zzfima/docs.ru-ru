---
title: "Устаревшие функции размещения CLR"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9530fecb4f2ca6f59d165e49c282320966fd2fa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="9f9f3-102">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9f9f3-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="9f9f3-103">В этом разделе описываются неуправляемые глобальные статические функции, которые используются в более ранних версиях API размещения.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="9f9f3-104">За исключением функций инфраструктуры (`_Cor*` функции), которые используются только платформой .NET Framework, эти функции являются устаревшими в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f9f3-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="9f9f3-105">Активация функции</span><span class="sxs-lookup"><span data-stu-id="9f9f3-105">Activation functions</span></span>  
 [<span data-ttu-id="9f9f3-106">ClrCreateManagedInstance-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="9f9f3-107">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-107">Deprecated.</span></span> <span data-ttu-id="9f9f3-108">Создает экземпляр указанного управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="9f9f3-109">Coinitializecor-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="9f9f3-110">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-110">Obsolete.</span></span> <span data-ttu-id="9f9f3-111">Чтобы инициализировать общеязыковой среды выполнения (CLR), используйте [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="9f9f3-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="9f9f3-112">Coinitializeee-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="9f9f3-113">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-113">Deprecated.</span></span> <span data-ttu-id="9f9f3-114">Обеспечивает загрузку ядро выполнения среды CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="9f9f3-115">Используйте [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="9f9f3-116">Corbindtocurrentruntime-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="9f9f3-117">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-117">Deprecated.</span></span> <span data-ttu-id="9f9f3-118">Загружает общеязыковой среды выполнения (CLR) в процесс, используя сведения, хранящиеся в XML-файл.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="9f9f3-119">CorBindToRuntime-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="9f9f3-120">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-120">Deprecated.</span></span> <span data-ttu-id="9f9f3-121">Позволяет неуправляемым узлам загрузить среду CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="9f9f3-122">CorBindToRuntimeByCfg-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="9f9f3-123">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-123">Deprecated.</span></span> <span data-ttu-id="9f9f3-124">Загружает среду CLR в процесс, используя сведения о версии, считываемые из файла XML.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="9f9f3-125">CorBindToRuntimeEx-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="9f9f3-126">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-126">Deprecated.</span></span> <span data-ttu-id="9f9f3-127">Позволяет неуправляемым узлам загрузить среду CLR в процессе и можно задавать флаги для задания поведения среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="9f9f3-128">CorBindToRuntimeHost-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="9f9f3-129">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-129">Deprecated.</span></span> <span data-ttu-id="9f9f3-130">Позволяет поставщикам услуг размещения для загрузки заданной версии среды CLR в процесс.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="9f9f3-131">Getcorrequiredversion-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="9f9f3-132">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-132">Deprecated.</span></span> <span data-ttu-id="9f9f3-133">Получает необходимые номер версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="9f9f3-134">Getcorsystemdirectory-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="9f9f3-135">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-135">Deprecated.</span></span> <span data-ttu-id="9f9f3-136">Возвращает каталог установки среды CLR, которая загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="9f9f3-137">Getrealprocaddress-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="9f9f3-138">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-138">Deprecated.</span></span> <span data-ttu-id="9f9f3-139">Получает адрес указанной функции, экспортированные из последней установленной версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="9f9f3-140">GetRequestedRuntimeInfo-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="9f9f3-141">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-141">Deprecated.</span></span> <span data-ttu-id="9f9f3-142">Получает сведения о версии и каталоге о среде CLR, запрошенный приложением.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="9f9f3-143">Версия функции CLR</span><span class="sxs-lookup"><span data-stu-id="9f9f3-143">CLR version functions</span></span>  
 <span data-ttu-id="9f9f3-144">В этом разделе возвращают версию среды CLR; они не активировать среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="9f9f3-145">Getcorversion-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="9f9f3-146">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-146">Deprecated.</span></span> <span data-ttu-id="9f9f3-147">Возвращает номер версии среды CLR, которая выполняется в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="9f9f3-148">Getfileversion-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="9f9f3-149">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-149">Deprecated.</span></span> <span data-ttu-id="9f9f3-150">Возвращает сведения о версии среды CLR для указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="9f9f3-151">GetRequestedRuntimeVersion-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="9f9f3-152">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-152">Deprecated.</span></span> <span data-ttu-id="9f9f3-153">Получает номер версии среды CLR, запрашиваемой указанным приложением.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="9f9f3-154">Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрошенной версии.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="9f9f3-155">Getrequestedruntimeversionforclsid-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="9f9f3-156">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-156">Deprecated.</span></span> <span data-ttu-id="9f9f3-157">Возвращает соответствующие сведения о версии среды CLR для класса с заданным идентификатором CLSID.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="9f9f3-158">GetVersionFromProcess-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="9f9f3-159">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-159">Deprecated.</span></span> <span data-ttu-id="9f9f3-160">Получает номер версии среды CLR, связанный с заданным дескриптором процесса.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="9f9f3-161">LockClrVersion-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="9f9f3-162">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-162">Deprecated.</span></span> <span data-ttu-id="9f9f3-163">Предоставляет узлу возможность определить, какие версии среды CLR, которая будет использоваться в процессе до явной инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="9f9f3-164">Функции размещения</span><span class="sxs-lookup"><span data-stu-id="9f9f3-164">Hosting functions</span></span>  
 [<span data-ttu-id="9f9f3-165">Callfunctionshim-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="9f9f3-166">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-166">Deprecated.</span></span> <span data-ttu-id="9f9f3-167">Выполняется вызов функции с указанным именем и параметрами в указанной библиотеке.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="9f9f3-168">CoEEShutDownCOM-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="9f9f3-169">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-169">Deprecated.</span></span> <span data-ttu-id="9f9f3-170">Выгружает сборку COM из процесса.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="9f9f3-171">CorExitProcess-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="9f9f3-172">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-172">Deprecated.</span></span> <span data-ttu-id="9f9f3-173">Завершает работу текущего неуправляемого процесса.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="9f9f3-174">Corlaunchapplication-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="9f9f3-175">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-175">Deprecated.</span></span> <span data-ttu-id="9f9f3-176">Запускает приложение по указанному сетевому пути, используя заданные манифесты и другие данные приложения.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="9f9f3-177">Cormarkthreadinthreadpool-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="9f9f3-178">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-178">Deprecated.</span></span> <span data-ttu-id="9f9f3-179">Помечает текущий выполняемый поток из пула потоков для выполнения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="9f9f3-180">Начиная с .NET Framework версии 2.0, эта функция не делает ничего.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="9f9f3-181">Он не является обязательным и может быть удален из кода.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="9f9f3-182">Couninitializecor-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="9f9f3-183">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-183">Obsolete.</span></span> <span data-ttu-id="9f9f3-184">Среда CLR не может быть выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="9f9f3-185">Couninitializeee-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="9f9f3-186">Является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="9f9f3-187">Функция CreateDebuggingInterfaceFromVersion</span><span class="sxs-lookup"><span data-stu-id="9f9f3-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="9f9f3-188">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-188">Deprecated.</span></span> <span data-ttu-id="9f9f3-189">Создает [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) объекта на основе указанной версии данных.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="9f9f3-190">Createiceefilegen-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="9f9f3-191">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-191">Deprecated.</span></span> <span data-ttu-id="9f9f3-192">Создает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="9f9f3-193">Destroyiceefilegen-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="9f9f3-194">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-194">Deprecated.</span></span> <span data-ttu-id="9f9f3-195">Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="9f9f3-196">Указатель функции FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="9f9f3-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="9f9f3-197">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-197">Deprecated.</span></span> <span data-ttu-id="9f9f3-198">Указывает на функцию, которую среда CLR вызывает на выполнение управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="9f9f3-199">Указатель функции FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="9f9f3-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="9f9f3-200">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-200">Deprecated.</span></span> <span data-ttu-id="9f9f3-201">Указывает на функцию, которая вызывается средой CLR для уведомления узла инициализации либо начала или завершения.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="9f9f3-202">Getclridentitymanager-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="9f9f3-203">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-203">Deprecated.</span></span> <span data-ttu-id="9f9f3-204">Возвращает указатель на интерфейс, который позволяет среде CLR для управления удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="9f9f3-205">LoadLibraryShim-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="9f9f3-206">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-206">Deprecated.</span></span> <span data-ttu-id="9f9f3-207">Загружает заданную версию библиотеки DLL, .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="9f9f3-208">Loadstringrc-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="9f9f3-209">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-209">Deprecated.</span></span> <span data-ttu-id="9f9f3-210">Преобразовывает значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="9f9f3-211">Loadstringrcex-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="9f9f3-212">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-212">Deprecated.</span></span> <span data-ttu-id="9f9f3-213">Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="9f9f3-214">LPOVERLAPPED_COMPLETION_ROUTINE-указатель функции</span><span class="sxs-lookup"><span data-stu-id="9f9f3-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="9f9f3-215">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-215">Deprecated.</span></span> <span data-ttu-id="9f9f3-216">Указывает на функцию, которая уведомляет основное приложение перекрывающегося (то есть асинхронные) завершения ввода-вывода на устройстве.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="9f9f3-217">LPTHREAD_START_ROUTINE-указатель функции</span><span class="sxs-lookup"><span data-stu-id="9f9f3-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="9f9f3-218">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-218">Deprecated.</span></span> <span data-ttu-id="9f9f3-219">Указывает на функцию, которая уведомляет основное приложение начала выполнения потока.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="9f9f3-220">Rundll32shimw-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="9f9f3-221">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-221">Deprecated.</span></span> <span data-ttu-id="9f9f3-222">Выполняет указанную команду.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="9f9f3-223">WAITORTIMERCALLBACK-указатель функции</span><span class="sxs-lookup"><span data-stu-id="9f9f3-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="9f9f3-224">Не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-224">Deprecated.</span></span> <span data-ttu-id="9f9f3-225">Указывает на функцию, которая уведомляет узел, что дескриптор ожидания был сигнал или истекло время ожидания.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="9f9f3-226">Функции инфраструктуры</span><span class="sxs-lookup"><span data-stu-id="9f9f3-226">Infrastructure functions</span></span>  
 <span data-ttu-id="9f9f3-227">Функции, в этом разделе предназначены для использования только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="9f9f3-228">_CorDllMain-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="9f9f3-229">Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR сборки DLL и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="9f9f3-230">_CorExeMain-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="9f9f3-231">Инициализирует среду CLR, размещает управляемую точку входа в заголовке среды CLR исполняемой сборки и начинает выполнение.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="9f9f3-232">_Corexemain2-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="9f9f3-233">Выполняет точка входа в заданный код, размещенный в памяти.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="9f9f3-234">Эта функция вызывается загрузчиком операционной системы.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="9f9f3-235">_CorImageUnloading-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="9f9f3-236">Уведомляет загрузчика при выгрузке образов управляемых модулей.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="9f9f3-237">_CorValidateImage-функция</span><span class="sxs-lookup"><span data-stu-id="9f9f3-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="9f9f3-238">Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.</span><span class="sxs-lookup"><span data-stu-id="9f9f3-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9f3-239">См. также</span><span class="sxs-lookup"><span data-stu-id="9f9f3-239">See Also</span></span>  
 [<span data-ttu-id="9f9f3-240">.NET framework 4 глобальные статические функции размещения</span><span class="sxs-lookup"><span data-stu-id="9f9f3-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
