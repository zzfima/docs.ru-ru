---
title: "Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa487ece58f228345188338fb61f1a2a85d9e4c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="c7145-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="c7145-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="c7145-103">Возвращает данные идентификации канонической сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="c7145-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7145-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7145-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7145-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7145-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="c7145-106">[in] Поток сборки должны быть оценены.</span><span class="sxs-lookup"><span data-stu-id="c7145-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c7145-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="c7145-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="c7145-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает текущую версию среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c7145-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="c7145-109">[out] Буфер, содержащий данные идентификации непрозрачный сборки.</span><span class="sxs-lookup"><span data-stu-id="c7145-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="c7145-110">[in, out] Размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="c7145-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7145-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c7145-111">Return Value</span></span>  
  
|<span data-ttu-id="c7145-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7145-112">HRESULT</span></span>|<span data-ttu-id="c7145-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c7145-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7145-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7145-114">S_OK</span></span>|<span data-ttu-id="c7145-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="c7145-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="c7145-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c7145-116">E_INVALIDARG</span></span>|<span data-ttu-id="c7145-117">Предоставленный `pStream` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="c7145-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="c7145-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="c7145-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="c7145-119">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="c7145-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="c7145-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7145-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7145-121">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c7145-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7145-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7145-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7145-123">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="c7145-123">The call timed out.</span></span>|  
|<span data-ttu-id="c7145-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7145-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7145-125">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="c7145-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7145-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7145-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7145-127">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="c7145-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7145-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7145-128">E_FAIL</span></span>|<span data-ttu-id="c7145-129">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="c7145-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7145-130">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c7145-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7145-131">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c7145-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7145-132">Требования</span><span class="sxs-lookup"><span data-stu-id="c7145-132">Requirements</span></span>  
 <span data-ttu-id="c7145-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7145-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7145-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c7145-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7145-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c7145-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7145-136">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7145-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7145-137">См. также</span><span class="sxs-lookup"><span data-stu-id="c7145-137">See Also</span></span>  
 [<span data-ttu-id="c7145-138">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="c7145-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="c7145-139">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="c7145-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
