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
ms.openlocfilehash: 7c3e37fdb8a5afc973c913b1cfa56ab2e9f4fa52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127730"
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="4aff1-102">Метод ICorRuntimeHost::CreateDomain</span><span class="sxs-lookup"><span data-stu-id="4aff1-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="4aff1-103">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="4aff1-103">Creates an application domain.</span></span> <span data-ttu-id="4aff1-104">Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> на экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4aff1-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aff1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4aff1-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4aff1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4aff1-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="4aff1-107">окне Необязательный параметр, используемый для присвоения понятного имени домену.</span><span class="sxs-lookup"><span data-stu-id="4aff1-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="4aff1-108">Это понятное имя может отображаться в пользовательских интерфейсах, таких как отладчики, для обнаружения домена.</span><span class="sxs-lookup"><span data-stu-id="4aff1-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="4aff1-109">окне Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное через политику безопасности для создания набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="4aff1-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="4aff1-110">Объект `IIdentity` можно получить, вызвав метод [креативиденце](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4aff1-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="4aff1-111">заполняет Указатель интерфейса типа <xref:System._AppDomain> на экземпляр <xref:System.AppDomain?displayProperty=nameWithType>, который может использоваться для дальнейшего управления доменом.</span><span class="sxs-lookup"><span data-stu-id="4aff1-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4aff1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4aff1-112">Return Value</span></span>  
  
|<span data-ttu-id="4aff1-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4aff1-113">HRESULT</span></span>|<span data-ttu-id="4aff1-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4aff1-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4aff1-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4aff1-115">S_OK</span></span>|<span data-ttu-id="4aff1-116">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="4aff1-116">The operation was successful.</span></span>|  
|<span data-ttu-id="4aff1-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4aff1-117">S_FALSE</span></span>|<span data-ttu-id="4aff1-118">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="4aff1-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="4aff1-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4aff1-119">E_FAIL</span></span>|<span data-ttu-id="4aff1-120">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="4aff1-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="4aff1-121">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="4aff1-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="4aff1-122">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4aff1-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4aff1-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4aff1-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4aff1-124">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="4aff1-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4aff1-125">Требования</span><span class="sxs-lookup"><span data-stu-id="4aff1-125">Requirements</span></span>  
 <span data-ttu-id="4aff1-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4aff1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aff1-127">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4aff1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4aff1-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4aff1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4aff1-129">**.NET Framework версии:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="4aff1-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aff1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4aff1-130">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="4aff1-131">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="4aff1-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
