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
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124470"
---
# <a name="ihostassemblystoreprovidemodule-method"></a><span data-ttu-id="028bf-102">Метод IHostAssemblyStore::ProvideModule</span><span class="sxs-lookup"><span data-stu-id="028bf-102">IHostAssemblyStore::ProvideModule Method</span></span>
<span data-ttu-id="028bf-103">Разрешает модуль в сборке или связанном (но не внедренном) файле ресурсов.</span><span class="sxs-lookup"><span data-stu-id="028bf-103">Resolves a module within an assembly or a linked (but not an embedded) resource file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="028bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="028bf-104">Syntax</span></span>  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="028bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="028bf-105">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="028bf-106">окне Указатель на экземпляр [модулебиндинфо](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) , описывающий <xref:System.AppDomain>, сборку и имя модуля запрошенного модуля.</span><span class="sxs-lookup"><span data-stu-id="028bf-106">[in] A pointer to a [ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md) instance that describes the requested module's <xref:System.AppDomain>, assembly, and module name.</span></span>  
  
 `pdwModuleId`  
 <span data-ttu-id="028bf-107">заполняет Указатель на уникальный идентификатор для `IStream`, содержащего загруженный модуль.</span><span class="sxs-lookup"><span data-stu-id="028bf-107">[out] A pointer to a unique identifier for the `IStream` containing the loaded module.</span></span>  
  
 `ppStmModuleImage`  
 <span data-ttu-id="028bf-108">заполняет Указатель на адрес объекта `IStream`, который содержит загружаемый переносимый исполняемый образ (PE), или значение null, если не удалось найти модуль.</span><span class="sxs-lookup"><span data-stu-id="028bf-108">[out] A pointer to the address of an `IStream` object, which contains the portable executable (PE) image to be loaded, or null if the module could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="028bf-109">заполняет Указатель на адрес объекта `IStream`, который содержит сведения о программе отладки (PDB) для запрошенного модуля, или значение null, если PDB-файл найти не удалось.</span><span class="sxs-lookup"><span data-stu-id="028bf-109">[out] A pointer to the address of an `IStream` object, which contains the program debug (PDB) information for the requested module, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="028bf-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="028bf-110">Return Value</span></span>  
  
|<span data-ttu-id="028bf-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="028bf-111">HRESULT</span></span>|<span data-ttu-id="028bf-112">Описание</span><span class="sxs-lookup"><span data-stu-id="028bf-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="028bf-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="028bf-113">S_OK</span></span>|<span data-ttu-id="028bf-114">`ProvideModule` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="028bf-114">`ProvideModule` returned successfully.</span></span>|  
|<span data-ttu-id="028bf-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="028bf-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="028bf-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="028bf-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="028bf-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="028bf-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="028bf-118">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="028bf-118">The call timed out.</span></span>|  
|<span data-ttu-id="028bf-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="028bf-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="028bf-120">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="028bf-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="028bf-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="028bf-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="028bf-122">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="028bf-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="028bf-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="028bf-123">E_FAIL</span></span>|<span data-ttu-id="028bf-124">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="028bf-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="028bf-125">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="028bf-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="028bf-126">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="028bf-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="028bf-127">COR_E_FILENOTFOUND (0x80070002)</span><span class="sxs-lookup"><span data-stu-id="028bf-127">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="028bf-128">Не удалось найти запрошенную сборку или связанный ресурс.</span><span class="sxs-lookup"><span data-stu-id="028bf-128">The requested assembly or linked resource could not be located.</span></span>|  
|<span data-ttu-id="028bf-129">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="028bf-129">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="028bf-130">`pdwModuleId` недостаточно велик, чтобы вместить идентификатор, который требуется вернуть узлу.</span><span class="sxs-lookup"><span data-stu-id="028bf-130">`pdwModuleId` is not large enough to contain the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="028bf-131">Заметки</span><span class="sxs-lookup"><span data-stu-id="028bf-131">Remarks</span></span>  
 <span data-ttu-id="028bf-132">Значение идентификатора, возвращаемое для `pdwModuleId`, задается узлом.</span><span class="sxs-lookup"><span data-stu-id="028bf-132">The identity value returned for `pdwModuleId` is specified by the host.</span></span> <span data-ttu-id="028bf-133">Идентификаторы должны быть уникальными в течение всего времени существования процесса.</span><span class="sxs-lookup"><span data-stu-id="028bf-133">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="028bf-134">Среда CLR использует это значение в качестве уникального идентификатора для связанного потока.</span><span class="sxs-lookup"><span data-stu-id="028bf-134">The CLR uses this value as the unique identifier for the associated stream.</span></span> <span data-ttu-id="028bf-135">Он проверяет каждое значение на соответствие значениям `pAssemblyId`, возвращаемых вызовами [провидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) , и значениями для `pdwModuleId`, возвращаемых другими вызовами метода `ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="028bf-135">It checks each value against the values for `pAssemblyId` returned by calls to [ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) and against the values for `pdwModuleId` returned by other calls to `ProvideModule`.</span></span> <span data-ttu-id="028bf-136">Если узел возвращает одно и то же значение идентификатора для другого `IStream`, среда CLR проверяет, было ли уже сопоставлено содержимое этого потока.</span><span class="sxs-lookup"><span data-stu-id="028bf-136">If the host returns the same identifier value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="028bf-137">Если это так, среда CLR загружает существующую копию изображения вместо сопоставления нового.</span><span class="sxs-lookup"><span data-stu-id="028bf-137">If so, the CLR loads the existing copy of the image instead of mapping a new one.</span></span> <span data-ttu-id="028bf-138">Таким образом, идентификатор также не должен пересекаться с идентификаторами сборки, возвращенными из `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="028bf-138">Therefore, the identifier must also not overlap with the assembly identifiers returned from `ProvideAssembly`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="028bf-139">Требования</span><span class="sxs-lookup"><span data-stu-id="028bf-139">Requirements</span></span>  
 <span data-ttu-id="028bf-140">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="028bf-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="028bf-141">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="028bf-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="028bf-142">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="028bf-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="028bf-143">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="028bf-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="028bf-144">См. также</span><span class="sxs-lookup"><span data-stu-id="028bf-144">See also</span></span>

- [<span data-ttu-id="028bf-145">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="028bf-145">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="028bf-146">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="028bf-146">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="028bf-147">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="028bf-147">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
