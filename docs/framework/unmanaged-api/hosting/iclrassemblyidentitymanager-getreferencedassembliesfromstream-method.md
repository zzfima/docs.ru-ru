---
title: Метод ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream method [.NET Framework hosting]
- GetReferencedAssembliesFromStream method [.NET Framework hosting]
ms.assetid: fe9849c1-c3fc-477b-a31f-e8619f5516f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9655981bf7ca21a6f59b305f6ea3fa5ff47f608a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773397"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromstream-method"></a><span data-ttu-id="9077a-102">Метод ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream</span><span class="sxs-lookup"><span data-stu-id="9077a-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromStream Method</span></span>
<span data-ttu-id="9077a-103">Возвращает указатель на [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) объект, содержащий данные идентификации сборки для сборки ссылается сборка в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="9077a-103">Gets a pointer to an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) object that contains assembly identity data for the assemblies referenced by the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9077a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9077a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReferencedAssembliesFromStream (  
    [in]  IStream *pStream,  
    [in]  DWORD    dwFlags,  
    [in]  ICLRAssemblyReferenceList  *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9077a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9077a-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="9077a-106">[in] Указатель интерфейса на `IStream` содержащим сборку для оценки.</span><span class="sxs-lookup"><span data-stu-id="9077a-106">[in] An interface pointer to an `IStream` containing the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9077a-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="9077a-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="9077a-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которая поддерживает текущая версия общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="9077a-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="9077a-109">[in] Указатель на [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , содержащий данные идентификации сборки для сборок, которые следует исключить из `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="9077a-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that contains assembly identity data for the assemblies to be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="9077a-110">[out] Указатель на адрес `ICLRReferenceAssemblyEnum` объект, содержащий данные идентификации сборки для сборки ссылается сборка в `pStream`, за исключением сборок в `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="9077a-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly in `pStream`, excluding the assemblies in `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9077a-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9077a-111">Return Value</span></span>  
  
|<span data-ttu-id="9077a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9077a-112">HRESULT</span></span>|<span data-ttu-id="9077a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9077a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9077a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9077a-114">S_OK</span></span>|<span data-ttu-id="9077a-115">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="9077a-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="9077a-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9077a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9077a-117">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9077a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9077a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9077a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9077a-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9077a-119">The call timed out.</span></span>|  
|<span data-ttu-id="9077a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9077a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9077a-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9077a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9077a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9077a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9077a-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9077a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9077a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9077a-124">E_FAIL</span></span>|<span data-ttu-id="9077a-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="9077a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9077a-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9077a-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9077a-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9077a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9077a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="9077a-128">Remarks</span></span>  
 <span data-ttu-id="9077a-129">Вызывающий объект можно исключить набор известных ссылок сборок в полученном списке.</span><span class="sxs-lookup"><span data-stu-id="9077a-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="9077a-130">Этот набор определяется `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="9077a-130">This set is defined by `pExcludeAssembliesList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9077a-131">Требования</span><span class="sxs-lookup"><span data-stu-id="9077a-131">Requirements</span></span>  
 <span data-ttu-id="9077a-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9077a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9077a-133">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9077a-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9077a-134">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9077a-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9077a-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9077a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9077a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9077a-136">See also</span></span>

- [<span data-ttu-id="9077a-137">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9077a-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9077a-138">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="9077a-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9077a-139">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="9077a-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
