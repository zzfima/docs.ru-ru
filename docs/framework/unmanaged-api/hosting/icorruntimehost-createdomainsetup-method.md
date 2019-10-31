---
title: Метод ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
ms.openlocfilehash: 217874e625604613e67170a118a7bc3616e02c4d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139645"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="ee144-102">Метод ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="ee144-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="ee144-103">Возвращает указатель интерфейса типа IAppDomainSetup на экземпляр <xref:System.AppDomainSetup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee144-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ee144-104">`IAppDomainSetup` предоставляет методы для настройки аспектов домена приложения перед его созданием.</span><span class="sxs-lookup"><span data-stu-id="ee144-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee144-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee144-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee144-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ee144-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="ee144-107">заполняет Указатель интерфейса на экземпляр <xref:System.AppDomainSetup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee144-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="ee144-108">Этот параметр типизирован как `IUnknown`, поэтому вызывающие объекты должны обычно вызывать `QueryInterface` для этого указателя, чтобы получить указатель интерфейса типа `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="ee144-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee144-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ee144-109">Return Value</span></span>  
  
|<span data-ttu-id="ee144-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee144-110">HRESULT</span></span>|<span data-ttu-id="ee144-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ee144-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee144-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee144-112">S_OK</span></span>|<span data-ttu-id="ee144-113">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="ee144-113">The operation was successful.</span></span>|  
|<span data-ttu-id="ee144-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ee144-114">S_FALSE</span></span>|<span data-ttu-id="ee144-115">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="ee144-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="ee144-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee144-116">E_FAIL</span></span>|<span data-ttu-id="ee144-117">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee144-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="ee144-118">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ee144-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="ee144-119">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ee144-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ee144-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee144-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee144-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ee144-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee144-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="ee144-122">Remarks</span></span>  
 <span data-ttu-id="ee144-123">Указатель, возвращаемый из этого метода, обычно передается в качестве параметра в метод [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ee144-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee144-124">Требования</span><span class="sxs-lookup"><span data-stu-id="ee144-124">Requirements</span></span>  
 <span data-ttu-id="ee144-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee144-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee144-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ee144-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee144-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee144-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee144-128">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="ee144-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee144-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ee144-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="ee144-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="ee144-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
