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
ms.openlocfilehash: 57cf4e9f79be8e705869cf986a586fcfb3359584
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435343"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="0b17d-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromStream</span><span class="sxs-lookup"><span data-stu-id="0b17d-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="0b17d-103">Возвращает данные идентификации канонической сборки для сборки в указанном потоке.</span><span class="sxs-lookup"><span data-stu-id="0b17d-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b17d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b17d-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b17d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b17d-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="0b17d-106">[in] Поток сборки должны быть оценены.</span><span class="sxs-lookup"><span data-stu-id="0b17d-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0b17d-107">[in] Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="0b17d-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="0b17d-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которое поддерживает текущую версию среды common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0b17d-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="0b17d-109">[out] Буфер, содержащий данные идентификации непрозрачный сборки.</span><span class="sxs-lookup"><span data-stu-id="0b17d-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="0b17d-110">[in, out] Размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0b17d-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b17d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b17d-111">Return Value</span></span>  
  
|<span data-ttu-id="0b17d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b17d-112">HRESULT</span></span>|<span data-ttu-id="0b17d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0b17d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b17d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0b17d-114">S_OK</span></span>|<span data-ttu-id="0b17d-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="0b17d-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="0b17d-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0b17d-116">E_INVALIDARG</span></span>|<span data-ttu-id="0b17d-117">Предоставленный `pStream` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="0b17d-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="0b17d-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0b17d-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="0b17d-119">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="0b17d-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="0b17d-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0b17d-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0b17d-121">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0b17d-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0b17d-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0b17d-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0b17d-123">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="0b17d-123">The call timed out.</span></span>|  
|<span data-ttu-id="0b17d-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0b17d-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0b17d-125">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="0b17d-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0b17d-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0b17d-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0b17d-127">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="0b17d-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0b17d-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0b17d-128">E_FAIL</span></span>|<span data-ttu-id="0b17d-129">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="0b17d-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0b17d-130">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="0b17d-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0b17d-131">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0b17d-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b17d-132">Требования</span><span class="sxs-lookup"><span data-stu-id="0b17d-132">Requirements</span></span>  
 <span data-ttu-id="0b17d-133">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b17d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b17d-134">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b17d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b17d-135">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b17d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b17d-136">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b17d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b17d-137">См. также</span><span class="sxs-lookup"><span data-stu-id="0b17d-137">See Also</span></span>  
 [<span data-ttu-id="0b17d-138">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="0b17d-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="0b17d-139">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="0b17d-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
