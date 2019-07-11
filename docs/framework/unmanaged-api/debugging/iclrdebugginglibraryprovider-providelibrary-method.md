---
title: Метод ICLRDebuggingLibraryProvider::ProvideLibrary
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26dbd7cb5f0dc3a385fe15d6c417d6fb8e1c9bc4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738351"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a><span data-ttu-id="ced6b-102">Метод ICLRDebuggingLibraryProvider::ProvideLibrary</span><span class="sxs-lookup"><span data-stu-id="ced6b-102">ICLRDebuggingLibraryProvider::ProvideLibrary Method</span></span>
<span data-ttu-id="ced6b-103">Получает поставщика библиотеки интерфейс обратного вызова, который позволяет среде выполнения (CLR) версии библиотеки отладки находить и загружать по требованию.</span><span class="sxs-lookup"><span data-stu-id="ced6b-103">Gets a library provider callback interface that allows common language runtime (CLR) version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ced6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ced6b-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ced6b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ced6b-105">Parameters</span></span>  
 `pwszFilename`  
 <span data-ttu-id="ced6b-106">[in] Имя запрашиваемого модуля.</span><span class="sxs-lookup"><span data-stu-id="ced6b-106">[in] The name of the module being requested.</span></span>  
  
 `dwTimestamp`  
 <span data-ttu-id="ced6b-107">[in] Отметку даты и времени в заголовке COFF файл PE-файлов.</span><span class="sxs-lookup"><span data-stu-id="ced6b-107">[in] The date time stamp stored in the COFF file header of PE files.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="ced6b-108">[in] `SizeOfImage` Поля в заголовке COFF необязательный файл PE-файлов.</span><span class="sxs-lookup"><span data-stu-id="ced6b-108">[in] The `SizeOfImage` field stored in the COFF optional file header of PE files.</span></span>  
  
 `hModule`  
 <span data-ttu-id="ced6b-109">[out] Дескриптор запрошенного модуля.</span><span class="sxs-lookup"><span data-stu-id="ced6b-109">[out] The handle to the requested module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ced6b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ced6b-110">Return Value</span></span>  
 <span data-ttu-id="ced6b-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="ced6b-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ced6b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ced6b-112">HRESULT</span></span>|<span data-ttu-id="ced6b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ced6b-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ced6b-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ced6b-114">S_OK</span></span>|<span data-ttu-id="ced6b-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ced6b-115">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ced6b-116">Исключения</span><span class="sxs-lookup"><span data-stu-id="ced6b-116">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ced6b-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="ced6b-117">Remarks</span></span>  
 <span data-ttu-id="ced6b-118">`ProvideLibrary` позволяет отладчику содержит модули, которые необходимы для отладки определенные файлы среды CLR, такие как mscordbi.dll и mscordacwks.dll.</span><span class="sxs-lookup"><span data-stu-id="ced6b-118">`ProvideLibrary` allows the debugger to provide modules that are needed for debugging specific CLR files such as mscordbi.dll and mscordacwks.dll.</span></span> <span data-ttu-id="ced6b-119">Дескрипторы модулей должны оставаться действительными до вызова [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) метод указывает, что их можно освободить, после чего это обязанность вызывающего для освобождения дескрипторов.</span><span class="sxs-lookup"><span data-stu-id="ced6b-119">The module handles have to remain valid until a call to the [ICLRDebugging::CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) method indicates that they may be freed, at which point it is the caller’s responsibility to free the handles.</span></span>  
  
 <span data-ttu-id="ced6b-120">Отладчик может использовать любые доступные средства поиска или получения модуля отладки.</span><span class="sxs-lookup"><span data-stu-id="ced6b-120">The debugger may use any available means to locate or procure the debugging module.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ced6b-121">Эта функция позволяет API вызывающего объекта предоставить модули, содержащие исполняемый файл и потенциально вредоносный код.</span><span class="sxs-lookup"><span data-stu-id="ced6b-121">This feature allows the API caller to provide modules that contain executable, and possibly malicious, code.</span></span> <span data-ttu-id="ced6b-122">По соображениям безопасности вызывающего объекта не следует использовать `ProvideLibrary` для распределения любого кода, что он не желает выполняться самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="ced6b-122">As a security precaution, the caller should not use `ProvideLibrary` to distribute any code that it is not willing to execute itself.</span></span>  
>   
>  <span data-ttu-id="ced6b-123">Если обнаружена серьезная угроза безопасности в уже выпущенной библиотеке, например mscordbi.dll или mscordacwks.dll, оболочка может быть исправлена для распознавания плохих версий файлов.</span><span class="sxs-lookup"><span data-stu-id="ced6b-123">If a serious security issue is discovered in an already released library, such as mscordbi.dll or mscordacwks.dll, the shim can be patched to recognize the bad versions of the files.</span></span> <span data-ttu-id="ced6b-124">Оболочки можно выполнять запросы к исправленных версий файлов и отвергать плохие версии, если они указаны в ответ на любой запрос.</span><span class="sxs-lookup"><span data-stu-id="ced6b-124">The shim can then issue requests for the patched versions of the files and reject the bad versions if they are provided in response to any request.</span></span> <span data-ttu-id="ced6b-125">Это может произойти только в том случае, если пользователь обновить до новой версии оболочки.</span><span class="sxs-lookup"><span data-stu-id="ced6b-125">This can occur only if the user has patched to a new version of the shim.</span></span> <span data-ttu-id="ced6b-126">Неисправленные версии будет оставаться уязвимыми.</span><span class="sxs-lookup"><span data-stu-id="ced6b-126">Unpatched versions will remain vulnerable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ced6b-127">Требования</span><span class="sxs-lookup"><span data-stu-id="ced6b-127">Requirements</span></span>  
 <span data-ttu-id="ced6b-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ced6b-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ced6b-129">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ced6b-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ced6b-130">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ced6b-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ced6b-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ced6b-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced6b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="ced6b-132">See also</span></span>

- [<span data-ttu-id="ced6b-133">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ced6b-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ced6b-134">Отладка</span><span class="sxs-lookup"><span data-stu-id="ced6b-134">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
