---
title: "Метод ICLRDebuggingLibraryProvider::ProvideLibrary"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cf6860a616312504e3d23177734cb532405bd714
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="eb855-102">Метод ICLRDebuggingLibraryProvider::ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="eb855-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="eb855-103">Возвращает поставщика библиотеки интерфейс обратного вызова, который позволяет среде (CLR) от версии библиотеки отладки находить и загружать по требованию.</span><span class="sxs-lookup"><span data-stu-id="eb855-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb855-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb855-104">Syntax</span></span>  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb855-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb855-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="eb855-106">[in] Имя запрашиваемого модуля.</span><span class="sxs-lookup"><span data-stu-id="eb855-106">[in] The name of the module being requested .</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="eb855-107">[in] Отметка времени даты, сохраненным в заголовке COFF файл PE-файлов.</span><span class="sxs-lookup"><span data-stu-id="eb855-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="eb855-108">[in] `SizeOfImage` Поля, сохраненным в заголовке COFF необязательный файл PE-файлов.</span><span class="sxs-lookup"><span data-stu-id="eb855-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="eb855-109">[out] Дескриптор запрошенного модуля.</span><span class="sxs-lookup"><span data-stu-id="eb855-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb855-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eb855-110">Return Value</span></span>  
 <span data-ttu-id="eb855-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="eb855-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="eb855-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb855-112">HRESULT</span></span>|<span data-ttu-id="eb855-113">Описание</span><span class="sxs-lookup"><span data-stu-id="eb855-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb855-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb855-114">S_OK</span></span>|<span data-ttu-id="eb855-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="eb855-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="eb855-116">Исключения</span><span class="sxs-lookup"><span data-stu-id="eb855-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb855-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb855-117">Remarks</span></span>  
 <span data-ttu-id="eb855-118">`ProvideLibrary`позволяет отладчику предоставляют модули, которые необходимы для отладки конкретных файлы среды CLR, такие как mscordbi.dll и mscordacwks.dll.</span><span class="sxs-lookup"><span data-stu-id="eb855-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="eb855-119">Дескрипторы модулей должны оставаться действительными до вызова [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) метод указывает, что их можно освободить, после чего он вызывающим для освобождения дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="eb855-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="eb855-120">Отладчик может использовать любые доступные средства поиска или получения модуля отладки.</span><span class="sxs-lookup"><span data-stu-id="eb855-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb855-121">Эта функция позволяет API вызывающему предоставлять модули, содержащие исполняемые и потенциально вредоносный код.</span><span class="sxs-lookup"><span data-stu-id="eb855-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="eb855-122">По соображениям безопасности не следует использовать код, вызывающий `ProvideLibrary` для распределения любого кода, что он не желает выполняться самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="eb855-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="eb855-123">Если обнаружено серьезную проблему безопасности в уже выпущенной библиотеке, например mscordbi.dll или mscordacwks.dll, оболочка может быть исправлена для распознавания плохих версий файлов.</span><span class="sxs-lookup"><span data-stu-id="eb855-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="eb855-124">Оболочки можно выполнять запросы к обновленной версии файлов и отвергать плохие версии, если они предоставляются в ответ на запрос.</span><span class="sxs-lookup"><span data-stu-id="eb855-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="eb855-125">Это может произойти только в том случае, если пользователь исправления до новой версии оболочки.</span><span class="sxs-lookup"><span data-stu-id="eb855-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="eb855-126">Неисправленные версии останутся незащищенными.</span><span class="sxs-lookup"><span data-stu-id="eb855-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb855-127">Требования</span><span class="sxs-lookup"><span data-stu-id="eb855-127">Requirements</span></span>  
 <span data-ttu-id="eb855-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb855-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb855-129">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb855-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb855-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb855-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb855-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb855-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb855-132">См. также</span><span class="sxs-lookup"><span data-stu-id="eb855-132">See Also</span></span>  
 [<span data-ttu-id="eb855-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="eb855-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="eb855-134">Отладка</span><span class="sxs-lookup"><span data-stu-id="eb855-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
