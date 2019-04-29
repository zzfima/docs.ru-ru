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
ms.openlocfilehash: e07e2c3f2c6000f5a081b13316c269f322b1ef8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599352"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="9be01-102">Метод IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="9be01-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="9be01-103">Разрешает файл ресурсов модуля в сборку или связанный (но не внедренный).</span><span class="sxs-lookup"><span data-stu-id="9be01-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be01-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9be01-104">Syntax</span></span>  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9be01-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9be01-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="9be01-106">[in] Указатель на [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) экземпляр, описывающий запрошенного модуля <xref:System.AppDomain>, сборки и имя модуля.</span><span class="sxs-lookup"><span data-stu-id="9be01-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="9be01-107">[out] Указатель на уникальный идентификатор для `IStream` содержащий загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="9be01-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="9be01-108">[out] Указатель на адрес `IStream` объекта, который содержит переносимого исполняемого (PE) образа загрузки, или значение null, если модуль не найден.</span><span class="sxs-lookup"><span data-stu-id="9be01-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="9be01-109">[out] Указатель на адрес `IStream` объекта, который содержит данные отладки (PDB) программы для запрошенного модуля, или значение null, если не удается найти PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="9be01-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9be01-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9be01-110">Return Value</span></span>  
  
|<span data-ttu-id="9be01-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9be01-111">HRESULT</span></span>|<span data-ttu-id="9be01-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9be01-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9be01-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="9be01-113">S_OK</span></span>|<span data-ttu-id="9be01-114">`ProvideModule` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9be01-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="9be01-115">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9be01-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9be01-116">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9be01-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9be01-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9be01-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9be01-118">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9be01-118">The call timed out.</span></span>|  
|<span data-ttu-id="9be01-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9be01-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9be01-120">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9be01-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9be01-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9be01-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9be01-122">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9be01-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9be01-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9be01-123">E_FAIL</span></span>|<span data-ttu-id="9be01-124">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="9be01-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9be01-125">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9be01-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9be01-126">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9be01-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9be01-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="9be01-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="9be01-128">Не удалось найти запрошенную сборку или связанного ресурса.</span><span class="sxs-lookup"><span data-stu-id="9be01-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="9be01-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9be01-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9be01-130">`pdwModuleId` не является достаточным для хранения идентификатора, который необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="9be01-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9be01-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="9be01-131">Remarks</span></span>  
 <span data-ttu-id="9be01-132">Возвращаемое значение identity для `pdwModuleId` указанным хостом.</span><span class="sxs-lookup"><span data-stu-id="9be01-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="9be01-133">Идентификаторы должны быть уникальными в пределах времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="9be01-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="9be01-134">Среда CLR использует это значение в качестве уникального идентификатора для соответствующего потока.</span><span class="sxs-lookup"><span data-stu-id="9be01-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="9be01-135">Она проверяет каждое значение со значениями для `pAssemblyId` возвращаемые вызовы [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) и со значениями для `pdwModuleId` возвращаемые других вызовов `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="9be01-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="9be01-136">Если узел возвращает то же значение идентификатора для другого `IStream`, среда CLR проверяет ли содержимое этого потока уже были сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="9be01-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="9be01-137">Если Да, среда CLR загружает имеющуюся копию образа вместо сопоставления нового.</span><span class="sxs-lookup"><span data-stu-id="9be01-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="9be01-138">Таким образом, идентификатор также не должен пересекаться с идентификаторы сборки, возвращенные из `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="9be01-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9be01-139">Требования</span><span class="sxs-lookup"><span data-stu-id="9be01-139">Requirements</span></span>  
 <span data-ttu-id="9be01-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9be01-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9be01-141">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9be01-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9be01-142">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9be01-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9be01-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be01-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be01-144">См. также</span><span class="sxs-lookup"><span data-stu-id="9be01-144">See also</span></span>

- [<span data-ttu-id="9be01-145">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="9be01-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9be01-146">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="9be01-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="9be01-147">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="9be01-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
