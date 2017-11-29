---
title: "Метод ICLRRuntimeInfo::IsStarted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsStarted
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d6bcaf6e0d10bd935e7ba4a2bb79941be1af6950
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="6569a-102">Метод ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="6569a-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="6569a-103">Указывает, была ли запущена среда выполнения (есть ли [ICLRRuntimeHost::Start-метод](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) был вызван и успешно).</span><span class="sxs-lookup"><span data-stu-id="6569a-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6569a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6569a-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6569a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6569a-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="6569a-106">[out] `true` Если эта среда выполнения запущен; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="6569a-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="6569a-107">[out] Возвращает флаги, которые были использованы для запуска среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="6569a-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6569a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6569a-108">Return Value</span></span>  
 <span data-ttu-id="6569a-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="6569a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6569a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6569a-110">HRESULT</span></span>|<span data-ttu-id="6569a-111">Описание</span><span class="sxs-lookup"><span data-stu-id="6569a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6569a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6569a-112">S_OK</span></span>|<span data-ttu-id="6569a-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="6569a-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="6569a-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="6569a-114">E_NOTIMPL</span></span>|<span data-ttu-id="6569a-115">В версии среды выполнения (CLR) более ранняя, чем версия CLR в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6569a-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6569a-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="6569a-116">Remarks</span></span>  
 <span data-ttu-id="6569a-117">Этот метод не работает с версиями среды CLR более ранних, чем версия CLR в [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6569a-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6569a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="6569a-118">Requirements</span></span>  
 <span data-ttu-id="6569a-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6569a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6569a-120">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6569a-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6569a-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6569a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6569a-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6569a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6569a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6569a-123">See Also</span></span>  
 [<span data-ttu-id="6569a-124">ICLRRuntimeInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6569a-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="6569a-125">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="6569a-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="6569a-126">Размещение</span><span class="sxs-lookup"><span data-stu-id="6569a-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
