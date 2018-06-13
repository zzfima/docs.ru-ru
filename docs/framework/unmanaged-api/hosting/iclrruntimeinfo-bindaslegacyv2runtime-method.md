---
title: Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690287bf54f98c19298504ee3058a59ef88a87f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433165"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="a68fd-102">Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="a68fd-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="a68fd-103">Привязывает текущую среду выполнения для всех устаревших общих языка среды CLR версии 2 решений политики активации.</span><span class="sxs-lookup"><span data-stu-id="a68fd-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a68fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a68fd-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a68fd-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a68fd-105">Return Value</span></span>  
 <span data-ttu-id="a68fd-106">Этот метод возвращает следующие конкретные результаты HRESULT:</span><span class="sxs-lookup"><span data-stu-id="a68fd-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="a68fd-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a68fd-107">HRESULT</span></span>|<span data-ttu-id="a68fd-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a68fd-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a68fd-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a68fd-109">S_OK</span></span>|<span data-ttu-id="a68fd-110">Привязка выполнена успешно, либо эта среда выполнения уже были привязаны как устаревшие версии 2 активации политики среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a68fd-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="a68fd-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="a68fd-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="a68fd-112">Другая среда выполнения уже была привязана к прежних версий среды CLR политике активации версии 2.</span><span class="sxs-lookup"><span data-stu-id="a68fd-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a68fd-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="a68fd-113">Remarks</span></span>  
 <span data-ttu-id="a68fd-114">Если текущей среды выполнения уже связана со всех предыдущих версий среды CLR версии 2 решений политики активации (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; Вместо этого результатом является значение S_OK, так же, как было бы, если метод успешно привязал устаревшей политике активации.</span><span class="sxs-lookup"><span data-stu-id="a68fd-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a68fd-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a68fd-115">Requirements</span></span>  
 <span data-ttu-id="a68fd-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a68fd-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a68fd-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a68fd-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a68fd-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a68fd-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a68fd-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a68fd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a68fd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a68fd-120">See Also</span></span>  
 [<span data-ttu-id="a68fd-121">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="a68fd-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="a68fd-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a68fd-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="a68fd-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="a68fd-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="a68fd-124">Элемент \<startup></span><span class="sxs-lookup"><span data-stu-id="a68fd-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
