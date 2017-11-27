---
title: "Метод IHostAssemblyStore::ProvideAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cda88c2e93b4f90844ad3dec2ed0fa4366dba6d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblystoreprovideassembly-method"></a><span data-ttu-id="ae473-102">Метод IHostAssemblyStore::ProvideAssembly</span><span class="sxs-lookup"><span data-stu-id="ae473-102">IHostAssemblyStore::ProvideAssembly Method</span></span>
<span data-ttu-id="ae473-103">Возвращает ссылку на сборку, которая не ссылается [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) возвращенный [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span><span class="sxs-lookup"><span data-stu-id="ae473-103">Gets a reference to an assembly that is not referenced by the [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that is returned from [IHostAssemblyManager::GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md).</span></span> <span data-ttu-id="ae473-104">Общеязыковая среда выполнения (CLR) вызывает `ProvideAssembly` для каждой сборки, которое не отображается в списке.</span><span class="sxs-lookup"><span data-stu-id="ae473-104">The common language runtime (CLR) calls `ProvideAssembly` for each assembly that does not appear in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae473-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae473-105">Syntax</span></span>  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae473-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae473-106">Parameters</span></span>  
 `pBindInfo`  
 <span data-ttu-id="ae473-107">[in] Указатель на [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) экземпляр, который узел использует для определения характеристики привязки, включая наличие или отсутствие все политики управления версиями и какие сборки для привязки.</span><span class="sxs-lookup"><span data-stu-id="ae473-107">[in] A pointer to an [AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md) instance that the host uses to determine certain bind characteristics, including the presence or absence of any versioning policy, and which assembly to bind to.</span></span>  
  
 `pAssemblyId`  
 <span data-ttu-id="ae473-108">[out] Указатель на уникальный идентификатор для запрашиваемой сборки для данного `IStream`.</span><span class="sxs-lookup"><span data-stu-id="ae473-108">[out] A pointer to a unique identifier for the requested assembly for this `IStream`.</span></span>  
  
 `pHostContext`  
 <span data-ttu-id="ae473-109">[out] Указатель на данные определенного узла, используемый для определения свидетельство запрошенную сборку без необходимости платформы вызова неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ae473-109">[out] A pointer to host-specific data that is used to determine the evidence of the requested assembly without the need of a platform invoke call.</span></span> <span data-ttu-id="ae473-110">`pHostContext`соответствует <xref:System.Reflection.Assembly.HostContext%2A> свойство управляемых <xref:System.Reflection.Assembly> класса.</span><span class="sxs-lookup"><span data-stu-id="ae473-110">`pHostContext` corresponds to the <xref:System.Reflection.Assembly.HostContext%2A> property of the managed <xref:System.Reflection.Assembly> class.</span></span>  
  
 `ppStmAssemblyImage`  
 <span data-ttu-id="ae473-111">[out] Указатель на адрес `IStream` , содержащий изображение переносимого исполняемого (PE) загружена, либо значение null, если не удалось найти сборку.</span><span class="sxs-lookup"><span data-stu-id="ae473-111">[out] A pointer to the address of an `IStream` that contains the portable executable (PE) image to be loaded, or null if the assembly could not be found.</span></span>  
  
 `ppStmPDB`  
 <span data-ttu-id="ae473-112">[out] Указатель на адрес `IStream` , содержащий сведения о программе отладки (PDB), или значение null, если не удается найти PDB-файл.</span><span class="sxs-lookup"><span data-stu-id="ae473-112">[out] A pointer to the address of an `IStream` that contains the program debug (PDB) information, or null if the .pdb file could not be found.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae473-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ae473-113">Return Value</span></span>  
  
|<span data-ttu-id="ae473-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae473-114">HRESULT</span></span>|<span data-ttu-id="ae473-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ae473-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae473-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae473-116">S_OK</span></span>|<span data-ttu-id="ae473-117">`ProvideAssembly`успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ae473-117">`ProvideAssembly` returned successfully.</span></span>|  
|<span data-ttu-id="ae473-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae473-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae473-119">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ae473-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ae473-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ae473-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ae473-121">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ae473-121">The call timed out.</span></span>|  
|<span data-ttu-id="ae473-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ae473-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ae473-123">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ae473-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ae473-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ae473-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ae473-125">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ae473-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ae473-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae473-126">E_FAIL</span></span>|<span data-ttu-id="ae473-127">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="ae473-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ae473-128">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ae473-128">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ae473-129">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ae473-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ae473-130">COR_E_FILENOTFOUND (0X80070002)</span><span class="sxs-lookup"><span data-stu-id="ae473-130">COR_E_FILENOTFOUND (0x80070002)</span></span>|<span data-ttu-id="ae473-131">Не удалось найти запрошенную сборку.</span><span class="sxs-lookup"><span data-stu-id="ae473-131">The requested assembly could not be located.</span></span>|  
|<span data-ttu-id="ae473-132">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ae473-132">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ae473-133">Размер буфера, заданный свойством `pAssemblyId` недостаточно велик для хранения с идентификатором, который необходимо вернуть.</span><span class="sxs-lookup"><span data-stu-id="ae473-133">The buffer size specified by `pAssemblyId` is not large enough to hold the identifier that the host wants to return.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae473-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="ae473-134">Remarks</span></span>  
 <span data-ttu-id="ae473-135">Возвращаемое значение идентификатора для `pAssemblyId` заданный главным узлом.</span><span class="sxs-lookup"><span data-stu-id="ae473-135">The identity value returned for `pAssemblyId` is specified by the host.</span></span> <span data-ttu-id="ae473-136">Идентификаторы должны быть уникальными в пределах срока существования процесса.</span><span class="sxs-lookup"><span data-stu-id="ae473-136">Identifiers must be unique within the lifetime of a process.</span></span> <span data-ttu-id="ae473-137">Среда CLR использует это значение в качестве уникального идентификатора для потока.</span><span class="sxs-lookup"><span data-stu-id="ae473-137">The CLR uses this value as a unique identifier for the stream.</span></span> <span data-ttu-id="ae473-138">Она проверяет каждое значение со значениями параметра `pAssemblyId` возвращенных другими вызовами `ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="ae473-138">It checks each value against the values for `pAssemblyId` returned by other calls to `ProvideAssembly`.</span></span> <span data-ttu-id="ae473-139">Если узел возвращает тот же `pAssemblyId` значение для другого `IStream`, среда CLR проверяет, является ли содержимое этого потока уже были сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="ae473-139">If the host returns the same `pAssemblyId` value for another `IStream`, the CLR checks whether the contents of that stream have already been mapped.</span></span> <span data-ttu-id="ae473-140">В этом случае среда выполнения загружает имеющуюся копию образа вместо сопоставления нового.</span><span class="sxs-lookup"><span data-stu-id="ae473-140">If so, the runtime loads the existing copy of the image instead of mapping a new one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae473-141">Требования</span><span class="sxs-lookup"><span data-stu-id="ae473-141">Requirements</span></span>  
 <span data-ttu-id="ae473-142">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae473-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae473-143">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ae473-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae473-144">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ae473-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae473-145">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae473-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae473-146">См. также</span><span class="sxs-lookup"><span data-stu-id="ae473-146">See Also</span></span>  
 [<span data-ttu-id="ae473-147">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ae473-147">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="ae473-148">Ihostassemblymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ae473-148">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="ae473-149">IHostAssemblyStore-интерфейс</span><span class="sxs-lookup"><span data-stu-id="ae473-149">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
