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
ms.openlocfilehash: c4db96133315b23a2d0b4bd32b597ee03f5d697b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438120"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="e2716-102">Метод ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="e2716-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="e2716-103">Выгружает заданный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="e2716-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2716-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2716-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2716-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2716-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="e2716-106">[in] Указатель типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен, который будет выгружен.</span><span class="sxs-lookup"><span data-stu-id="e2716-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2716-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2716-107">Return Value</span></span>  
  
|<span data-ttu-id="e2716-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e2716-108">HRESULT</span></span>|<span data-ttu-id="e2716-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e2716-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e2716-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2716-110">S_OK</span></span>|<span data-ttu-id="e2716-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="e2716-111">The operation was successful.</span></span>|  
|<span data-ttu-id="e2716-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e2716-112">S_FALSE</span></span>|<span data-ttu-id="e2716-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="e2716-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e2716-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e2716-114">E_FAIL</span></span>|<span data-ttu-id="e2716-115">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e2716-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e2716-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e2716-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e2716-117">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e2716-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e2716-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e2716-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e2716-119">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e2716-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2716-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e2716-120">Requirements</span></span>  
 <span data-ttu-id="e2716-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2716-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2716-122">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2716-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2716-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2716-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2716-124">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e2716-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2716-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e2716-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="e2716-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e2716-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
