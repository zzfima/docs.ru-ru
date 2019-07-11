---
title: Метод ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55f3bd89f0ca177bcd4edef2e17a7d2256a0042a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773490"
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="906ed-102">Метод ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference</span><span class="sxs-lookup"><span data-stu-id="906ed-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="906ed-103">Получает [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) перечислителя для идентификаторов сборки ссылается сборка с заданным типом идентификации.</span><span class="sxs-lookup"><span data-stu-id="906ed-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="906ed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="906ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="906ed-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="906ed-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="906ed-106">[in] Допустимое значение, указывающее архитектура процессора, как определено в заголовке WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="906ed-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="906ed-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="906ed-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="906ed-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которая поддерживает текущая версия общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="906ed-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="906ed-109">[in] Удостоверение привязки непрозрачный сборки, обычно возвращается из вызова [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) или [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="906ed-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="906ed-110">[out] Указатель интерфейса на `ICLRProbingAssemblyEnum` перечислителя, который содержит ссылки на сборки ссылается сборка идентифицируется `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="906ed-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="906ed-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="906ed-111">Return Value</span></span>  
  
|<span data-ttu-id="906ed-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="906ed-112">HRESULT</span></span>|<span data-ttu-id="906ed-113">Описание</span><span class="sxs-lookup"><span data-stu-id="906ed-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="906ed-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="906ed-114">S_OK</span></span>|<span data-ttu-id="906ed-115">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="906ed-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="906ed-116">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="906ed-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="906ed-117">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="906ed-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="906ed-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="906ed-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="906ed-119">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="906ed-119">The call timed out.</span></span>|  
|<span data-ttu-id="906ed-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="906ed-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="906ed-121">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="906ed-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="906ed-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="906ed-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="906ed-123">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="906ed-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="906ed-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="906ed-124">E_FAIL</span></span>|<span data-ttu-id="906ed-125">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="906ed-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="906ed-126">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="906ed-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="906ed-127">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="906ed-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="906ed-128">Требования</span><span class="sxs-lookup"><span data-stu-id="906ed-128">Requirements</span></span>  
 <span data-ttu-id="906ed-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="906ed-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="906ed-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="906ed-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="906ed-131">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="906ed-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="906ed-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="906ed-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906ed-133">См. также</span><span class="sxs-lookup"><span data-stu-id="906ed-133">See also</span></span>

- [<span data-ttu-id="906ed-134">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="906ed-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="906ed-135">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="906ed-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="906ed-136">Интерфейс ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="906ed-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
