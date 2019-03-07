---
title: Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b094c37368e3b6515518d94fbdbf5033ec74b90f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484723"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="9e45d-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="9e45d-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="9e45d-103">Получает идентификатор сборки привязка данных для сборки по указанному пути.</span><span class="sxs-lookup"><span data-stu-id="9e45d-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e45d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e45d-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e45d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e45d-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="9e45d-106">[in] Путь к файлу для оценки.</span><span class="sxs-lookup"><span data-stu-id="9e45d-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9e45d-107">[in] Значение [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) перечисление, указывающее тип удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="9e45d-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="9e45d-108">Предоставлен для дальнейшего расширения.</span><span class="sxs-lookup"><span data-stu-id="9e45d-108">Provided for future extensibility.</span></span> <span data-ttu-id="9e45d-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT является единственным значением, которая поддерживает общеязыковой среды выполнения (CLR) версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="9e45d-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="9e45d-110">[out] Буфер, содержащий данные идентификации непрозрачный сборки.</span><span class="sxs-lookup"><span data-stu-id="9e45d-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="9e45d-111">[in, out] Указатель на размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9e45d-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e45d-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e45d-112">Return Value</span></span>  
  
|<span data-ttu-id="9e45d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9e45d-113">HRESULT</span></span>|<span data-ttu-id="9e45d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9e45d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e45d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9e45d-115">S_OK</span></span>|<span data-ttu-id="9e45d-116">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="9e45d-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="9e45d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9e45d-117">E_INVALIDARG</span></span>|<span data-ttu-id="9e45d-118">Предоставленный `pwzFilePath` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="9e45d-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="9e45d-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9e45d-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9e45d-120">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="9e45d-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="9e45d-121">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9e45d-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9e45d-122">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9e45d-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9e45d-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9e45d-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9e45d-124">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="9e45d-124">The call timed out.</span></span>|  
|<span data-ttu-id="9e45d-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9e45d-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9e45d-126">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="9e45d-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9e45d-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9e45d-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9e45d-128">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="9e45d-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9e45d-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9e45d-129">E_FAIL</span></span>|<span data-ttu-id="9e45d-130">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="9e45d-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9e45d-131">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9e45d-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9e45d-132">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9e45d-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e45d-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e45d-133">Remarks</span></span>  
 <span data-ttu-id="9e45d-134">`GetBindingIdentityFromFile` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="9e45d-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="9e45d-135">Первый вызов предоставляет значение null для `pwzBuffer`, а метод возвращает соответствующий размер в `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="9e45d-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="9e45d-136">При втором вызове указывается надлежащий выделенный буфер, а метод возвращает фактические данные буфера после завершения.</span><span class="sxs-lookup"><span data-stu-id="9e45d-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e45d-137">Требования</span><span class="sxs-lookup"><span data-stu-id="9e45d-137">Requirements</span></span>  
 <span data-ttu-id="9e45d-138">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e45d-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e45d-139">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9e45d-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e45d-140">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e45d-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e45d-141">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e45d-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e45d-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9e45d-142">See also</span></span>
- [<span data-ttu-id="9e45d-143">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9e45d-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9e45d-144">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="9e45d-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9e45d-145">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="9e45d-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
