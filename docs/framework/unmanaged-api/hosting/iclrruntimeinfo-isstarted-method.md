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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 432de909e1b8166f6d8923889382d9408fb6c62d
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490261"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="648ca-102">Метод ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="648ca-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="648ca-103">Указывает, был ли запущен среды выполнения (то есть ли [метод ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) был вызван и успешно).</span><span class="sxs-lookup"><span data-stu-id="648ca-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="648ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="648ca-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="648ca-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="648ca-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="648ca-106">[out] `true` Если эта среда выполнения работы, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="648ca-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="648ca-107">[out] Возвращает флаги, которые использовались для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="648ca-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="648ca-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="648ca-108">Return Value</span></span>  
 <span data-ttu-id="648ca-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="648ca-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="648ca-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="648ca-110">HRESULT</span></span>|<span data-ttu-id="648ca-111">Описание</span><span class="sxs-lookup"><span data-stu-id="648ca-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="648ca-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="648ca-112">S_OK</span></span>|<span data-ttu-id="648ca-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="648ca-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="648ca-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="648ca-114">E_NOTIMPL</span></span>|<span data-ttu-id="648ca-115">В версии среды выполнения (CLR) более ранняя, чем версия среды CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="648ca-115">The common language runtime (CLR) version is earlier than the CLR version in the .NET Framework 4.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="648ca-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="648ca-116">Remarks</span></span>  
 <span data-ttu-id="648ca-117">Этот метод не работает с CLR версии более ранней, чем версия среды CLR в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="648ca-117">This method does not work with CLR versions earlier than the CLR version in the .NET Framework 4.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="648ca-118">Требования</span><span class="sxs-lookup"><span data-stu-id="648ca-118">Requirements</span></span>  
 <span data-ttu-id="648ca-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="648ca-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="648ca-120">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="648ca-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="648ca-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="648ca-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="648ca-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="648ca-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648ca-123">См. также</span><span class="sxs-lookup"><span data-stu-id="648ca-123">See also</span></span>

- [<span data-ttu-id="648ca-124">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="648ca-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="648ca-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="648ca-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="648ca-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="648ca-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
