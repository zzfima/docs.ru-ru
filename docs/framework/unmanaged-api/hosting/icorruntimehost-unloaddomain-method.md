---
title: Метод ICorRuntimeHost::UnloadDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90c845d87cc9c8bf229dd604ec2077ec28d31dcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770783"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="17af9-102">Метод ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="17af9-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="17af9-103">Выгружает указанный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="17af9-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17af9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17af9-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17af9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="17af9-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="17af9-106">[in] Указатель типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен, к выгрузке.</span><span class="sxs-lookup"><span data-stu-id="17af9-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17af9-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="17af9-107">Return Value</span></span>  
  
|<span data-ttu-id="17af9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17af9-108">HRESULT</span></span>|<span data-ttu-id="17af9-109">Описание</span><span class="sxs-lookup"><span data-stu-id="17af9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17af9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="17af9-110">S_OK</span></span>|<span data-ttu-id="17af9-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="17af9-111">The operation was successful.</span></span>|  
|<span data-ttu-id="17af9-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="17af9-112">S_FALSE</span></span>|<span data-ttu-id="17af9-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="17af9-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="17af9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17af9-114">E_FAIL</span></span>|<span data-ttu-id="17af9-115">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="17af9-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="17af9-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="17af9-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="17af9-117">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="17af9-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="17af9-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="17af9-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="17af9-119">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="17af9-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17af9-120">Требования</span><span class="sxs-lookup"><span data-stu-id="17af9-120">Requirements</span></span>  
 <span data-ttu-id="17af9-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17af9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17af9-122">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="17af9-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17af9-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17af9-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17af9-124">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="17af9-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17af9-125">См. также</span><span class="sxs-lookup"><span data-stu-id="17af9-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="17af9-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="17af9-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
