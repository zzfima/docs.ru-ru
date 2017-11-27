---
title: "Метод ICLRRuntimeInfo::GetInterface"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type: apiref
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0049b4e60f803fbc9ec64e7f20273b1d5729e67f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="a187e-102">Метод ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="a187e-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="a187e-103">Загружает среду CLR в текущий процесс и возвращает среды выполнения указателей интерфейса, такие как [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), и [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a187e-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="a187e-104">Этот метод заменяет все `CorBindTo`* функции в [устаревшие функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="a187e-104">This method supersedes all the `CorBindTo`* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a187e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a187e-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a187e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a187e-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="a187e-107">[in] Интерфейс CLSID для компонентного класса.</span><span class="sxs-lookup"><span data-stu-id="a187e-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="a187e-108">[in] Идентификатор IID запрошенного `rclsid` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="a187e-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="a187e-109">[out] Указатель на запрашиваемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a187e-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a187e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a187e-110">Return Value</span></span>  
 <span data-ttu-id="a187e-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="a187e-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a187e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a187e-112">HRESULT</span></span>|<span data-ttu-id="a187e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a187e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a187e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a187e-114">S_OK</span></span>|<span data-ttu-id="a187e-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="a187e-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="a187e-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a187e-116">E_POINTER</span></span>|<span data-ttu-id="a187e-117">Параметр `ppUnk` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a187e-117">`ppUnk` is null.</span></span>|  
|<span data-ttu-id="a187e-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a187e-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a187e-119">Недостаточно памяти для обработки запроса.</span><span class="sxs-lookup"><span data-stu-id="a187e-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="a187e-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="a187e-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="a187e-121">Другая среда выполнения уже была привязана к прежних версий среды CLR политике активации версии 2.</span><span class="sxs-lookup"><span data-stu-id="a187e-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a187e-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="a187e-122">Remarks</span></span>  
 <span data-ttu-id="a187e-123">Этот метод вызывает средой CLR с целью загружено, но не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="a187e-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="a187e-124">В следующей таблице показаны поддерживаемые сочетания для `rclsid` и `riid`.</span><span class="sxs-lookup"><span data-stu-id="a187e-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="a187e-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="a187e-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="a187e-126">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="a187e-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="a187e-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="a187e-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="a187e-128">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="a187e-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="a187e-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a187e-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="a187e-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a187e-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="a187e-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a187e-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="a187e-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="a187e-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="a187e-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="a187e-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="a187e-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="a187e-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="a187e-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="a187e-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="a187e-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a187e-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="a187e-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a187e-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="a187e-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a187e-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a187e-139">Требования</span><span class="sxs-lookup"><span data-stu-id="a187e-139">Requirements</span></span>  
 <span data-ttu-id="a187e-140">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a187e-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a187e-141">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a187e-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a187e-142">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a187e-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a187e-143">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a187e-143">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a187e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="a187e-144">See Also</span></span>  
 [<span data-ttu-id="a187e-145">ICLRRuntimeInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a187e-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="a187e-146">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a187e-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a187e-147">Размещение</span><span class="sxs-lookup"><span data-stu-id="a187e-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
