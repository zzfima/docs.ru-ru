---
title: Метод ICorRuntimeHost::CreateDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 662a47f75f2eef75b39ee877ea4645311cae6210
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484879"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="827a2-102">Метод ICorRuntimeHost::CreateDomain</span><span class="sxs-lookup"><span data-stu-id="827a2-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="827a2-103">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="827a2-103">Creates an application domain.</span></span> <span data-ttu-id="827a2-104">Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> для экземпляра типа <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="827a2-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="827a2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="827a2-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="827a2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="827a2-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="827a2-107">[in] Необязательный параметр, используемый нужно присвоить понятное имя домена.</span><span class="sxs-lookup"><span data-stu-id="827a2-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="827a2-108">Это понятное имя может отображаться в пользовательском интерфейсе, такие как отладчики для определения домена.</span><span class="sxs-lookup"><span data-stu-id="827a2-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="827a2-109">[in] Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное посредством политики безопасности для установления набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="827a2-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="827a2-110">`IIdentity` Может быть получен путем вызова [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="827a2-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="827a2-111">[out] Указатель интерфейса типа <xref:System._AppDomain> к экземпляру <xref:System.AppDomain?displayProperty=nameWithType> , можно использовать для последующего управления домена.</span><span class="sxs-lookup"><span data-stu-id="827a2-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="827a2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="827a2-112">Return Value</span></span>  
  
|<span data-ttu-id="827a2-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="827a2-113">HRESULT</span></span>|<span data-ttu-id="827a2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="827a2-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="827a2-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="827a2-115">S_OK</span></span>|<span data-ttu-id="827a2-116">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="827a2-116">The operation was successful.</span></span>|  
|<span data-ttu-id="827a2-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="827a2-117">S_FALSE</span></span>|<span data-ttu-id="827a2-118">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="827a2-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="827a2-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="827a2-119">E_FAIL</span></span>|<span data-ttu-id="827a2-120">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="827a2-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="827a2-121">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="827a2-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="827a2-122">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="827a2-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="827a2-123">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="827a2-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="827a2-124">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="827a2-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="827a2-125">Требования</span><span class="sxs-lookup"><span data-stu-id="827a2-125">Requirements</span></span>  
 <span data-ttu-id="827a2-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="827a2-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="827a2-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="827a2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="827a2-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="827a2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="827a2-129">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="827a2-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827a2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="827a2-130">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="827a2-131">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="827a2-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
