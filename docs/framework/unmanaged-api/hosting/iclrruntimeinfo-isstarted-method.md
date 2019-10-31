---
title: Метод ICLRRuntimeInfo::IsStarted
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 34590744407b25d7d53c06c452fff5bac2a95246
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136390"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="9d80f-102">Метод ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="9d80f-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="9d80f-103">Указывает, была ли запущена среда выполнения (т. е. был ли вызван [метод ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) и он был успешно выполнен).</span><span class="sxs-lookup"><span data-stu-id="9d80f-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d80f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d80f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d80f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d80f-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="9d80f-106">[out] `true`, если эта среда выполнения запущена; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9d80f-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="9d80f-107">заполняет Возвращает флаги, которые использовались для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9d80f-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d80f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9d80f-108">Return Value</span></span>  
 <span data-ttu-id="9d80f-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="9d80f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9d80f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d80f-110">HRESULT</span></span>|<span data-ttu-id="9d80f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9d80f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d80f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d80f-112">S_OK</span></span>|<span data-ttu-id="9d80f-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="9d80f-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="9d80f-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9d80f-114">E_NOTIMPL</span></span>|<span data-ttu-id="9d80f-115">Версия среды CLR предшествует версии CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9d80f-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d80f-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="9d80f-116">Remarks</span></span>  
 <span data-ttu-id="9d80f-117">Этот метод не работает с версиями CLR, предшествующими версии CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9d80f-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d80f-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9d80f-118">Requirements</span></span>  
 <span data-ttu-id="9d80f-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d80f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d80f-120">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="9d80f-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d80f-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9d80f-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d80f-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d80f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d80f-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9d80f-123">See also</span></span>

- [<span data-ttu-id="9d80f-124">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="9d80f-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="9d80f-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9d80f-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9d80f-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="9d80f-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
