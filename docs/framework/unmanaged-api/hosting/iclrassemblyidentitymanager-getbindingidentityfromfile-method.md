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
ms.openlocfilehash: 19d6a76d62680be91a7b9721912ca528edde7511
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126757"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="9c717-102">Метод ICLRAssemblyIdentityManager::GetBindingIdentityFromFile</span><span class="sxs-lookup"><span data-stu-id="9c717-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="9c717-103">Возвращает данные привязки удостоверения сборки для сборки по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="9c717-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c717-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c717-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c717-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c717-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="9c717-106">окне Путь к файлу, который необходимо вычислить.</span><span class="sxs-lookup"><span data-stu-id="9c717-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9c717-107">окне Значение перечисления [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) , указывающее тип удостоверения сборки.</span><span class="sxs-lookup"><span data-stu-id="9c717-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="9c717-108">Предоставляется для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="9c717-108">Provided for future extensibility.</span></span> <span data-ttu-id="9c717-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT — единственное значение, поддерживаемое общеязыковой средой выполнения (CLR) версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="9c717-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="9c717-110">заполняет Буфер, содержащий непрозрачные данные идентификации сборки.</span><span class="sxs-lookup"><span data-stu-id="9c717-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="9c717-111">[вход, выход] Указатель на размер `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="9c717-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c717-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c717-112">Return Value</span></span>  
  
|<span data-ttu-id="9c717-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c717-113">HRESULT</span></span>|<span data-ttu-id="9c717-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9c717-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c717-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c717-115">S_OK</span></span>|<span data-ttu-id="9c717-116">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="9c717-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="9c717-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9c717-117">E_INVALIDARG</span></span>|<span data-ttu-id="9c717-118">Указанный `pwzFilePath` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="9c717-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="9c717-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9c717-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9c717-120">Размер `pwzBuffer` слишком мал.</span><span class="sxs-lookup"><span data-stu-id="9c717-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="9c717-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c717-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c717-122">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="9c717-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c717-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c717-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c717-124">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="9c717-124">The call timed out.</span></span>|  
|<span data-ttu-id="9c717-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c717-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c717-126">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="9c717-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c717-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c717-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c717-128">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="9c717-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c717-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c717-129">E_FAIL</span></span>|<span data-ttu-id="9c717-130">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="9c717-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c717-131">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="9c717-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c717-132">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9c717-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c717-133">Заметки</span><span class="sxs-lookup"><span data-stu-id="9c717-133">Remarks</span></span>  
 <span data-ttu-id="9c717-134">`GetBindingIdentityFromFile` обычно вызывается дважды.</span><span class="sxs-lookup"><span data-stu-id="9c717-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="9c717-135">Первый вызов предоставляет значение NULL для `pwzBuffer`, а метод возвращает соответствующий размер в `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="9c717-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="9c717-136">Второй вызов предоставляет соответствующий буфер, а метод возвращает фактические данные буфера после завершения.</span><span class="sxs-lookup"><span data-stu-id="9c717-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c717-137">Требования</span><span class="sxs-lookup"><span data-stu-id="9c717-137">Requirements</span></span>  
 <span data-ttu-id="9c717-138">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c717-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c717-139">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9c717-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c717-140">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9c717-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c717-141">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c717-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c717-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9c717-142">See also</span></span>

- [<span data-ttu-id="9c717-143">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9c717-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9c717-144">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="9c717-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9c717-145">Интерфейс ICLRHostBindingPolicyManager</span><span class="sxs-lookup"><span data-stu-id="9c717-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
