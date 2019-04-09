---
title: Метод ICLRRuntimeInfo::GetInterface
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetInterface
helpviewer_keywords:
- GetInterface method [.NET Framework hosting]
- ICLRRuntimeInfo::GetInterface method [.NET Framework hosting]
ms.assetid: cc7b0e5b-48c3-4509-8ebb-611ddb1f7ec2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f229e421cc69f2ff45110233c4c6c36d7a1fc4c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152754"
---
# <a name="iclrruntimeinfogetinterface-method"></a><span data-ttu-id="5c508-102">Метод ICLRRuntimeInfo::GetInterface</span><span class="sxs-lookup"><span data-stu-id="5c508-102">ICLRRuntimeInfo::GetInterface Method</span></span>
<span data-ttu-id="5c508-103">Загружает среду CLR в текущий процесс и возвращает среды выполнения, указатели на интерфейс, такие как [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), и [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c508-103">Loads the CLR into the current process and returns runtime interface pointers, such as [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md), and [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md).</span></span>  
  
 <span data-ttu-id="5c508-104">Этот метод заменяет все `CorBindTo`\* функции в [устаревшей функции размещения CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) раздел.</span><span class="sxs-lookup"><span data-stu-id="5c508-104">This method supersedes all the `CorBindTo`\* functions in the [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c508-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c508-105">Syntax</span></span>  
  
```  
HRESULT GetInterface(  
[in]  REFCLSID rclsid,  
[in]  REFIID   riid,  
[out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c508-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c508-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="5c508-107">[in] Интерфейс CLSID для компонентного класса.</span><span class="sxs-lookup"><span data-stu-id="5c508-107">[in] The CLSID interface for the coclass.</span></span>  
  
 `riid`  
 <span data-ttu-id="5c508-108">[in] Идентификатор IID запрошенного `rclsid` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5c508-108">[in] The IID of the requested `rclsid` interface.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="5c508-109">[out] Указатель на запрашиваемый интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5c508-109">[out] A pointer to the queried interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c508-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5c508-110">Return Value</span></span>  
 <span data-ttu-id="5c508-111">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5c508-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5c508-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c508-112">HRESULT</span></span>|<span data-ttu-id="5c508-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5c508-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c508-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c508-114">S_OK</span></span>|<span data-ttu-id="5c508-115">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="5c508-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="5c508-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5c508-116">E_POINTER</span></span>|`ppUnk` <span data-ttu-id="5c508-117">имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="5c508-117">is null.</span></span>|  
|<span data-ttu-id="5c508-118">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5c508-118">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5c508-119">Недостаточно памяти для обработки запроса.</span><span class="sxs-lookup"><span data-stu-id="5c508-119">Not enough memory is available to handle the request.</span></span>|  
|<span data-ttu-id="5c508-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="5c508-120">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="5c508-121">Другие среды выполнения уже была привязана к устаревшая политика активации 2 версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5c508-121">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c508-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c508-122">Remarks</span></span>  
 <span data-ttu-id="5c508-123">Этот метод вызывает среды CLR загружено, но не инициализирован.</span><span class="sxs-lookup"><span data-stu-id="5c508-123">This method causes the CLR to be loaded but not initialized.</span></span>  
  
 <span data-ttu-id="5c508-124">В следующей таблице показаны поддерживаемые сочетания для `rclsid` и `riid`.</span><span class="sxs-lookup"><span data-stu-id="5c508-124">The following table shows the supported combinations for `rclsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="5c508-125">CLSID_CorMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="5c508-125">CLSID_CorMetaDataDispenser</span></span>|<span data-ttu-id="5c508-126">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5c508-126">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="5c508-127">CLSID_CorMetaDataDispenserRuntime</span><span class="sxs-lookup"><span data-stu-id="5c508-127">CLSID_CorMetaDataDispenserRuntime</span></span>|<span data-ttu-id="5c508-128">IID_IMetaDataDispenser IID_IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="5c508-128">IID_IMetaDataDispenser, IID_IMetaDataDispenserEx</span></span>|  
|<span data-ttu-id="5c508-129">CLSID_CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5c508-129">CLSID_CorRuntimeHost</span></span>|<span data-ttu-id="5c508-130">IID_ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5c508-130">IID_ICorRuntimeHost</span></span>|  
|<span data-ttu-id="5c508-131">CLSID_CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5c508-131">CLSID_CLRRuntimeHost</span></span>|<span data-ttu-id="5c508-132">IID_ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="5c508-132">IID_ICLRRuntimeHost</span></span>|  
|<span data-ttu-id="5c508-133">CLSID_TypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="5c508-133">CLSID_TypeNameFactory</span></span>|<span data-ttu-id="5c508-134">IID_ITypeNameFactory</span><span class="sxs-lookup"><span data-stu-id="5c508-134">IID_ITypeNameFactory</span></span>|  
|<span data-ttu-id="5c508-135">CLSID_CLRDebuggingLegacy</span><span class="sxs-lookup"><span data-stu-id="5c508-135">CLSID_CLRDebuggingLegacy</span></span>|<span data-ttu-id="5c508-136">IID_ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5c508-136">IID_ICorDebug</span></span>|  
|||  
|<span data-ttu-id="5c508-137">CLSID_CLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5c508-137">CLSID_CLRStrongName</span></span>|<span data-ttu-id="5c508-138">IID_ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5c508-138">IID_ICLRStrongName</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c508-139">Требования</span><span class="sxs-lookup"><span data-stu-id="5c508-139">Requirements</span></span>  
 <span data-ttu-id="5c508-140">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c508-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c508-141">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5c508-141">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5c508-142">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c508-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5c508-143">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c508-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c508-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5c508-144">See also</span></span>

- [<span data-ttu-id="5c508-145">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="5c508-145">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5c508-146">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5c508-146">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5c508-147">Размещение</span><span class="sxs-lookup"><span data-stu-id="5c508-147">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
