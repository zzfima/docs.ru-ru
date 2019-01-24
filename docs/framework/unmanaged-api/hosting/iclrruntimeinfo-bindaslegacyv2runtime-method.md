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
ms.openlocfilehash: 6c85888e9d29e7b3ae6ad76d1e534e08a4603ed2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499029"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="49283-102">Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="49283-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="49283-103">Привязывает текущую среду выполнения для всех устаревших распространенных языка среды выполнения (CLR) версии 2 активации решения на основе политик.</span><span class="sxs-lookup"><span data-stu-id="49283-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49283-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49283-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="49283-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49283-105">Return Value</span></span>  
 <span data-ttu-id="49283-106">Этот метод возвращает следующие специфичные результаты HRESULT:</span><span class="sxs-lookup"><span data-stu-id="49283-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="49283-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49283-107">HRESULT</span></span>|<span data-ttu-id="49283-108">Описание</span><span class="sxs-lookup"><span data-stu-id="49283-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49283-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="49283-109">S_OK</span></span>|<span data-ttu-id="49283-110">Привязка выполнена успешно, либо эта среда выполнения уже были привязаны как старой среды выполнения CLR версии 2 активации политики.</span><span class="sxs-lookup"><span data-stu-id="49283-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="49283-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="49283-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="49283-112">Другие среды выполнения уже была привязана к устаревшая политика активации 2 версии среды CLR.</span><span class="sxs-lookup"><span data-stu-id="49283-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49283-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="49283-113">Remarks</span></span>  
 <span data-ttu-id="49283-114">Если для всех предыдущих версий среды CLR версии 2 решений политики активации уже привязано текущей среды выполнения (например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибут [ \<запуска > элемент](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки; Вместо этого возвращается значение S_OK, так же, как было бы, если метод успешно привязал устаревшей политике активации.</span><span class="sxs-lookup"><span data-stu-id="49283-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49283-115">Требования</span><span class="sxs-lookup"><span data-stu-id="49283-115">Requirements</span></span>  
 <span data-ttu-id="49283-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49283-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49283-117">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="49283-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="49283-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49283-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49283-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49283-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49283-120">См. также</span><span class="sxs-lookup"><span data-stu-id="49283-120">See also</span></span>
- [<span data-ttu-id="49283-121">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="49283-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="49283-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="49283-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="49283-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="49283-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="49283-124">Элемент \<startup></span><span class="sxs-lookup"><span data-stu-id="49283-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
