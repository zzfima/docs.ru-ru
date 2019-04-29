---
title: Функция CLRCreateInstance
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3571e2698b980b12b89a5b689efb868a34a3ef71
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789614"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="f48a4-102">Функция CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="f48a4-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="f48a4-103">Предоставляет один из трех интерфейсов: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), или [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f48a4-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f48a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f48a4-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f48a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f48a4-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="f48a4-106">[in] Один из трех классов идентификаторов: Аргументами CLSID_CLRMetaHost CLSID_CLRMetaHostPolicy и CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="f48a4-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="f48a4-107">[in] Один из трех идентификаторы интерфейса (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy или IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="f48a4-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="f48a4-108">[out] Один из трех интерфейсов: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), или [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f48a4-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f48a4-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f48a4-109">Return Value</span></span>  
 <span data-ttu-id="f48a4-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="f48a4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f48a4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f48a4-111">HRESULT</span></span>|<span data-ttu-id="f48a4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f48a4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f48a4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f48a4-113">S_OK</span></span>|<span data-ttu-id="f48a4-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f48a4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f48a4-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f48a4-115">E_POINTER</span></span>|<span data-ttu-id="f48a4-116">Параметр `ppInterface` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="f48a4-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f48a4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f48a4-117">Remarks</span></span>  
 <span data-ttu-id="f48a4-118">В следующей таблице показаны поддерживаемые сочетания для `clsid` и `riid`.</span><span class="sxs-lookup"><span data-stu-id="f48a4-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="f48a4-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="f48a4-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="f48a4-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="f48a4-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="f48a4-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="f48a4-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="f48a4-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="f48a4-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="f48a4-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="f48a4-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="f48a4-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="f48a4-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="f48a4-125">Ниже показано, как использовать `CLRCreateInstance` получить все три интерфейса:</span><span class="sxs-lookup"><span data-stu-id="f48a4-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f48a4-126">Требования</span><span class="sxs-lookup"><span data-stu-id="f48a4-126">Requirements</span></span>  
 <span data-ttu-id="f48a4-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f48a4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f48a4-128">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f48a4-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f48a4-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f48a4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f48a4-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f48a4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f48a4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f48a4-131">See also</span></span>

- [<span data-ttu-id="f48a4-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="f48a4-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
