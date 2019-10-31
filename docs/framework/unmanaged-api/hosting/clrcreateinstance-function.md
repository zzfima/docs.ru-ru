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
ms.openlocfilehash: c1d796c6ef5f707f865a60023899d3b451c2085b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131958"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="8d616-102">Функция CLRCreateInstance</span><span class="sxs-lookup"><span data-stu-id="8d616-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="8d616-103">Предоставляет один из трех интерфейсов: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)или [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8d616-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d616-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d616-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d616-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d616-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="8d616-106">окне Один из трех идентификаторов класса: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy или CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="8d616-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="8d616-107">окне Один из трех идентификаторов интерфейса (идентификаторов IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy или IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="8d616-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="8d616-108">заполняет Один из трех интерфейсов: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)или [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8d616-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d616-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8d616-109">Return Value</span></span>  
 <span data-ttu-id="8d616-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8d616-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8d616-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d616-111">HRESULT</span></span>|<span data-ttu-id="8d616-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8d616-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d616-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d616-113">S_OK</span></span>|<span data-ttu-id="8d616-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8d616-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="8d616-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8d616-115">E_POINTER</span></span>|<span data-ttu-id="8d616-116">Параметр `ppInterface` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="8d616-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d616-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="8d616-117">Remarks</span></span>  
 <span data-ttu-id="8d616-118">В следующей таблице приведены поддерживаемые сочетания для `clsid` и `riid`.</span><span class="sxs-lookup"><span data-stu-id="8d616-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="8d616-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="8d616-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="8d616-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="8d616-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="8d616-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="8d616-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="8d616-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="8d616-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="8d616-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="8d616-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="8d616-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="8d616-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="8d616-125">В следующем коде показано, как использовать `CLRCreateInstance` для получения всех трех интерфейсов:</span><span class="sxs-lookup"><span data-stu-id="8d616-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
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
  
## <a name="requirements"></a><span data-ttu-id="8d616-126">Требования</span><span class="sxs-lookup"><span data-stu-id="8d616-126">Requirements</span></span>  
 <span data-ttu-id="8d616-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d616-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d616-128">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8d616-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8d616-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8d616-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d616-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d616-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d616-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8d616-131">See also</span></span>

- [<span data-ttu-id="8d616-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="8d616-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
