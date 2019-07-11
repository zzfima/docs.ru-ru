---
title: Метод IHostAssemblyStore::ProvideModule
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9290fd70b17b5a6456d85cb4b037ebbc62e028f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763974"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="35038-102">Метод IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="35038-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="35038-103">Разрешает файл ресурсов модуля в сборку или связанный (но не внедренный).</span><span class="sxs-lookup"><span data-stu-id="35038-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35038-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35038-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35038-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35038-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="35038-106">[in] Указатель на [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) экземпляр, описывающий запрошенного модуля <xref:System.AppDomain>, сборки и имя модуля.</span><span class="sxs-lookup"><span data-stu-id="35038-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="35038-107">[out] Указатель на уникальный идентификатор для `IStream` содержащий загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="35038-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="35038-108">[out] Указатель на адрес `IStream` объекта, который содержит переносимого исполняемого (PE) образа загрузки, или значение null, если модуль не найден.</span><span class="sxs-lookup"><span data-stu-id="35038-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="35038-109">[out] Указатель на адрес `IStream` объекта, который содержит данные отладки (PDB) программы для запрошенного модуля, или значение null, если не удается найти PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="35038-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35038-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="35038-110">Return Value</span></span>  
  
|<span data-ttu-id="35038-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35038-111">HRESULT</span></span>|<span data-ttu-id="35038-112">Описание</span><span class="sxs-lookup"><span data-stu-id="35038-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35038-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="35038-113">S_OK</span></span>|<span data-ttu-id="35038-114">`ProvideModule` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="35038-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="35038-115">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="35038-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="35038-116">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="35038-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="35038-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35038-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="35038-118">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="35038-118">The call timed out.</span></span>|  
|<span data-ttu-id="35038-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="35038-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="35038-120">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="35038-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="35038-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="35038-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="35038-122">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="35038-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="35038-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35038-123">E_FAIL</span></span>|<span data-ttu-id="35038-124">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="35038-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="35038-125">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="35038-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="35038-126">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="35038-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="35038-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="35038-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="35038-128">Не удалось найти запрошенную сборку или связанного ресурса.</span><span class="sxs-lookup"><span data-stu-id="35038-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="35038-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="35038-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="35038-130">`pdwModuleId` не является достаточным для хранения идентификатора, который необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="35038-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35038-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="35038-131">Remarks</span></span>  
 <span data-ttu-id="35038-132">Возвращаемое значение identity для `pdwModuleId` указанным хостом.</span><span class="sxs-lookup"><span data-stu-id="35038-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="35038-133">Идентификаторы должны быть уникальными в пределах времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="35038-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="35038-134">Среда CLR использует это значение в качестве уникального идентификатора для соответствующего потока.</span><span class="sxs-lookup"><span data-stu-id="35038-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="35038-135">Она проверяет каждое значение со значениями для `pAssemblyId` возвращаемые вызовы [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) и со значениями для `pdwModuleId` возвращаемые других вызовов `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="35038-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="35038-136">Если узел возвращает то же значение идентификатора для другого `IStream`, среда CLR проверяет ли содержимое этого потока уже были сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="35038-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="35038-137">Если Да, среда CLR загружает имеющуюся копию образа вместо сопоставления нового.</span><span class="sxs-lookup"><span data-stu-id="35038-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="35038-138">Таким образом, идентификатор также не должен пересекаться с идентификаторы сборки, возвращенные из `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="35038-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35038-139">Требования</span><span class="sxs-lookup"><span data-stu-id="35038-139">Requirements</span></span>  
 <span data-ttu-id="35038-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35038-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35038-141">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35038-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35038-142">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35038-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35038-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35038-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35038-144">См. также</span><span class="sxs-lookup"><span data-stu-id="35038-144">See also</span></span>

- [<span data-ttu-id="35038-145">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="35038-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="35038-146">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="35038-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="35038-147">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="35038-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
