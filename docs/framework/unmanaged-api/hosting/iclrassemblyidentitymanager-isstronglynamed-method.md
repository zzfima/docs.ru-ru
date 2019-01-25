---
title: Метод ICLRAssemblyIdentityManager::IsStronglyNamed
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.IsStronglyNamed
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::IsStronglyNamed
helpviewer_keywords:
- IsStronglyNamed method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::IsStronglyNamed method [.NET Framework hosting]
ms.assetid: 954bd386-2076-4d00-9d46-38c728aa9cab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a958e38857d2407930cb8c03a08eabdf6574cda9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563898"
---
# <a name="iclrassemblyidentitymanagerisstronglynamed-method"></a><span data-ttu-id="f5a85-102">Метод ICLRAssemblyIdentityManager::IsStronglyNamed</span><span class="sxs-lookup"><span data-stu-id="f5a85-102">ICLRAssemblyIdentityManager::IsStronglyNamed Method</span></span>
<span data-ttu-id="f5a85-103">Получает значение, указывающее, является ли указанная сборка имеет строгое имя.</span><span class="sxs-lookup"><span data-stu-id="f5a85-103">Gets a value that indicates whether the specified assembly is strongly named.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5a85-104">Syntax</span></span>  
  
```  
RESULT IsStronglyNamed (  
    [in]  LPCWSTR  pwzAssemblyIdentity,  
    [out] BOOL    *pbIsStronglyNamed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5a85-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5a85-105">Parameters</span></span>  
 `pwzAssemblyIdentity`  
 <span data-ttu-id="f5a85-106">[in] Непрозрачный канонические данные идентификации сборки, необходимо оценить.</span><span class="sxs-lookup"><span data-stu-id="f5a85-106">[in] The opaque canonical assembly identity data of the assembly to be evaluated.</span></span>  
  
 `pbIsStronglyNamed`  
 <span data-ttu-id="f5a85-107">[out] `true`, если ссылка на сборку с `pwzAssemblyIdentity` параметр строго имя; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f5a85-107">[out] `true`, if the assembly referenced by the `pwzAssemblyIdentity` parameter is strongly named; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5a85-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f5a85-108">Return Value</span></span>  
  
|<span data-ttu-id="f5a85-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5a85-109">HRESULT</span></span>|<span data-ttu-id="f5a85-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f5a85-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5a85-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5a85-111">S_OK</span></span>|<span data-ttu-id="f5a85-112">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="f5a85-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="f5a85-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f5a85-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f5a85-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="f5a85-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f5a85-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f5a85-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f5a85-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="f5a85-116">The call timed out.</span></span>|  
|<span data-ttu-id="f5a85-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f5a85-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f5a85-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="f5a85-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f5a85-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f5a85-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f5a85-120">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="f5a85-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f5a85-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f5a85-121">E_FAIL</span></span>|<span data-ttu-id="f5a85-122">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="f5a85-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f5a85-123">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="f5a85-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f5a85-124">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f5a85-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5a85-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f5a85-125">Requirements</span></span>  
 <span data-ttu-id="f5a85-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a85-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a85-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5a85-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5a85-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5a85-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5a85-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a85-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a85-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f5a85-130">See also</span></span>
- [<span data-ttu-id="f5a85-131">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f5a85-131">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
