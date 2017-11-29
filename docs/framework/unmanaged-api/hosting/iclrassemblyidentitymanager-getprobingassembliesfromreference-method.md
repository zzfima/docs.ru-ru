---
title: "Метод ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80ffc1cb4c1387aae673ec757b846c7075e20b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="96b4c-102">Метод ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="96b4c-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="96b4c-103">Возвращает [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) перечислителя для идентификаторов сборки ссылается сборка с заданным типом идентификации.</span><span class="sxs-lookup"><span data-stu-id="96b4c-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96b4c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96b4c-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96b4c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96b4c-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="96b4c-106">[in] Допустимое значение, указывающее архитектуру процессора, определенный в заголовке WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="96b4c-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="96b4c-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="96b4c-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает текущую версию среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="96b4c-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="96b4c-109">[in] Идентификатор привязки непрозрачный сборки, обычно возвращаемые при вызове для [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) или [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="96b4c-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="96b4c-110">[out] Указатель интерфейса `ICLRProbingAssemblyEnum` перечислителя, который содержит ссылки на сборки ссылается сборка определяется `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96b4c-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="96b4c-111">Return Value</span></span>  
  
|<span data-ttu-id="96b4c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="96b4c-112">HRESULT</span></span>|<span data-ttu-id="96b4c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="96b4c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="96b4c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="96b4c-114">S_OK</span></span>|<span data-ttu-id="96b4c-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="96b4c-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="96b4c-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="96b4c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="96b4c-117">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="96b4c-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="96b4c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="96b4c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="96b4c-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="96b4c-119">The call timed out.</span></span>|  
|<span data-ttu-id="96b4c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="96b4c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="96b4c-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="96b4c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="96b4c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="96b4c-123">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="96b4c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="96b4c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="96b4c-124">E_FAIL</span></span>|<span data-ttu-id="96b4c-125">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="96b4c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="96b4c-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="96b4c-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="96b4c-127">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="96b4c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96b4c-128">Требования</span><span class="sxs-lookup"><span data-stu-id="96b4c-128">Requirements</span></span>  
 <span data-ttu-id="96b4c-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96b4c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96b4c-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96b4c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96b4c-131">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96b4c-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96b4c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b4c-133">См. также</span><span class="sxs-lookup"><span data-stu-id="96b4c-133">See Also</span></span>  
 [<span data-ttu-id="96b4c-134">Iclrassemblyidentitymanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="96b4c-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="96b4c-135">ICLRAssemblyReferenceList-интерфейс</span><span class="sxs-lookup"><span data-stu-id="96b4c-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="96b4c-136">ICLRProbingAssemblyEnum-интерфейс</span><span class="sxs-lookup"><span data-stu-id="96b4c-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
