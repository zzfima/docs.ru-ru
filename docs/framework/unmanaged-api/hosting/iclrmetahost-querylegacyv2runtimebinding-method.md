---
title: Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd58d38e92f492522008745384459045e007c3ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646845"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="78f40-102">Метод ICLRMetaHost::QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="78f40-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>
<span data-ttu-id="78f40-103">Возвращает интерфейс, представляющий среду выполнения, к которому устаревшей политике активации привязки, например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<startup > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) запись файла конфигурации, напрямую используя Устаревшие интерфейсы API активации или вызывая [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="78f40-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f40-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78f40-104">Syntax</span></span>  
  
```  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78f40-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78f40-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="78f40-106">[in] Единственным допустимым значением для этого параметра является Required.Currently `IID_ICLRRuntimeInfo`.</span><span class="sxs-lookup"><span data-stu-id="78f40-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="78f40-107">[out] Обязательный.</span><span class="sxs-lookup"><span data-stu-id="78f40-107">[out] Required.</span></span> <span data-ttu-id="78f40-108">При возвращении данного метода содержит указатель на [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс, представляющий среду выполнения, привязанное к устаревшей политике активации.</span><span class="sxs-lookup"><span data-stu-id="78f40-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78f40-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="78f40-109">Return Value</span></span>  
 <span data-ttu-id="78f40-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="78f40-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="78f40-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78f40-111">HRESULT</span></span>|<span data-ttu-id="78f40-112">Описание</span><span class="sxs-lookup"><span data-stu-id="78f40-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78f40-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="78f40-113">S_OK</span></span>|<span data-ttu-id="78f40-114">Метод успешно выполнен, и возвращена среда выполнения, которая была привязана к устаревшей политике активации.</span><span class="sxs-lookup"><span data-stu-id="78f40-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="78f40-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="78f40-115">S_FALSE</span></span>|<span data-ttu-id="78f40-116">Метод успешно выполнен, но устаревшая среда выполнения еще не привязана.</span><span class="sxs-lookup"><span data-stu-id="78f40-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="78f40-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="78f40-117">E_NOINTERFACE</span></span>|<span data-ttu-id="78f40-118">Метод обнаружил среду выполнения, которая была привязана к устаревшей политике активации, но параметр `riid` не поддерживается этой средой.</span><span class="sxs-lookup"><span data-stu-id="78f40-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78f40-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="78f40-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f40-120">Требования</span><span class="sxs-lookup"><span data-stu-id="78f40-120">Requirements</span></span>  
 <span data-ttu-id="78f40-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78f40-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78f40-122">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="78f40-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="78f40-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="78f40-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78f40-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f40-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f40-125">См. также</span><span class="sxs-lookup"><span data-stu-id="78f40-125">See also</span></span>
- [<span data-ttu-id="78f40-126">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="78f40-126">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="78f40-127">Размещение</span><span class="sxs-lookup"><span data-stu-id="78f40-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
