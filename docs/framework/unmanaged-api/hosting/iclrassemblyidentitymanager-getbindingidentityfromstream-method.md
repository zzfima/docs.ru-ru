---
title: Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6590b455717dfdb3ea43e3622b494e2169047337
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469617"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="ab17e-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="ab17e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="ab17e-103">Получает данные идентификации канонической сборки для сборки в заданном потоке.</span><span class="sxs-lookup"><span data-stu-id="ab17e-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab17e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab17e-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab17e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab17e-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="ab17e-106">[in] Поток сборки необходимо оценить.</span><span class="sxs-lookup"><span data-stu-id="ab17e-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ab17e-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="ab17e-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="ab17e-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которая поддерживает текущая версия общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="ab17e-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="ab17e-109">[out] Буфер, содержащий данные идентификации непрозрачный сборки.</span><span class="sxs-lookup"><span data-stu-id="ab17e-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="ab17e-110">[in, out] Размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="ab17e-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab17e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab17e-111">Return Value</span></span>  
  
|<span data-ttu-id="ab17e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab17e-112">HRESULT</span></span>|<span data-ttu-id="ab17e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ab17e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab17e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab17e-114">S_OK</span></span>|<span data-ttu-id="ab17e-115">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="ab17e-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="ab17e-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ab17e-116">E_INVALIDARG</span></span>|<span data-ttu-id="ab17e-117">Предоставленный `pStream` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="ab17e-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="ab17e-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ab17e-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ab17e-119">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="ab17e-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="ab17e-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ab17e-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ab17e-121">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ab17e-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ab17e-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ab17e-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ab17e-123">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ab17e-123">The call timed out.</span></span>|  
|<span data-ttu-id="ab17e-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ab17e-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ab17e-125">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ab17e-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ab17e-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ab17e-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ab17e-127">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ab17e-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ab17e-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ab17e-128">E_FAIL</span></span>|<span data-ttu-id="ab17e-129">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="ab17e-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ab17e-130">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ab17e-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ab17e-131">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ab17e-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ab17e-132">Требования</span><span class="sxs-lookup"><span data-stu-id="ab17e-132">Requirements</span></span>  
 <span data-ttu-id="ab17e-133">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab17e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab17e-134">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ab17e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ab17e-135">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab17e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab17e-136">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab17e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab17e-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ab17e-137">See also</span></span>
- [<span data-ttu-id="ab17e-138">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ab17e-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ab17e-139">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ab17e-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
