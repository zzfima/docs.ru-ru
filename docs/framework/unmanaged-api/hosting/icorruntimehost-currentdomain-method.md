---
title: "Метод ICorRuntimeHost::CurrentDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CurrentDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CurrentDomain
helpviewer_keywords:
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
- CurrentDomain method [.NET Framework hosting]
ms.assetid: dd2afb38-675b-4c3c-a9f3-8ab3b133eb02
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 592b604f5e873f479f2e0489144240c3f021c270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcurrentdomain-method"></a><span data-ttu-id="2d96d-102">Метод ICorRuntimeHost::CurrentDomain</span><span class="sxs-lookup"><span data-stu-id="2d96d-102">ICorRuntimeHost::CurrentDomain Method</span></span>
<span data-ttu-id="2d96d-103">Получает указатель интерфейса типа <xref:System.AppDomain?displayProperty=nameWithType> , представляющий домен, который загружен в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="2d96d-103">Gets an interface pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the domain loaded on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d96d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d96d-104">Syntax</span></span>  
  
```  
HRESULT CurrentDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d96d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2d96d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2d96d-106">[out] Указатель типа <xref:System.AppDomain?displayProperty=nameWithType> , представляющий потока текущего домена приложения.</span><span class="sxs-lookup"><span data-stu-id="2d96d-106">[out] A pointer of type <xref:System.AppDomain?displayProperty=nameWithType> that represents the thread's current application domain.</span></span> <span data-ttu-id="2d96d-107">Этот указатель является типизированным `IUnknown`, поэтому обычно следует вызывать вызывающим объектам `QueryInterface` для получения указателя типа <xref:System._AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="2d96d-107">This pointer is typed `IUnknown`, so callers should generally call `QueryInterface` to obtain a pointer of type <xref:System._AppDomain>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d96d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2d96d-108">Return Value</span></span>  
  
|<span data-ttu-id="2d96d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d96d-109">HRESULT</span></span>|<span data-ttu-id="2d96d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="2d96d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d96d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2d96d-111">S_OK</span></span>|<span data-ttu-id="2d96d-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="2d96d-112">The operation was successful.</span></span>|  
|<span data-ttu-id="2d96d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2d96d-113">S_FALSE</span></span>|<span data-ttu-id="2d96d-114">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="2d96d-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2d96d-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2d96d-115">E_FAIL</span></span>|<span data-ttu-id="2d96d-116">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="2d96d-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2d96d-117">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2d96d-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2d96d-118">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2d96d-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2d96d-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2d96d-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2d96d-120">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2d96d-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d96d-121">Требования</span><span class="sxs-lookup"><span data-stu-id="2d96d-121">Requirements</span></span>  
 <span data-ttu-id="2d96d-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d96d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d96d-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2d96d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2d96d-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2d96d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2d96d-125">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2d96d-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d96d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2d96d-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="2d96d-127">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2d96d-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
