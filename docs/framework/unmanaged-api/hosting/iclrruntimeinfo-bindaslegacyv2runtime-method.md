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
ms.openlocfilehash: d37ec8e17e62f58212a5f79f4d6b6aa75f57bf7c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120258"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="55e3c-102">Метод ICLRRuntimeInfo::BindAsLegacyV2Runtime</span><span class="sxs-lookup"><span data-stu-id="55e3c-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="55e3c-103">Привязывает текущую среду выполнения для всех устаревших решений политики активации среды CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="55e3c-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55e3c-104">Syntax</span></span>  
  
```cpp  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="55e3c-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55e3c-105">Return Value</span></span>  
 <span data-ttu-id="55e3c-106">Этот метод возвращает следующие определенные значения HRESULT:</span><span class="sxs-lookup"><span data-stu-id="55e3c-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="55e3c-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55e3c-107">HRESULT</span></span>|<span data-ttu-id="55e3c-108">Описание</span><span class="sxs-lookup"><span data-stu-id="55e3c-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55e3c-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="55e3c-109">S_OK</span></span>|<span data-ttu-id="55e3c-110">Либо привязка выполнена успешно, либо эта среда выполнения уже была привязана к устаревшей среде выполнения политики активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="55e3c-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="55e3c-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="55e3c-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="55e3c-112">Другая среда выполнения уже привязана к устаревшей политике активации CLR версии 2.</span><span class="sxs-lookup"><span data-stu-id="55e3c-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55e3c-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="55e3c-113">Remarks</span></span>  
 <span data-ttu-id="55e3c-114">Если текущая среда выполнения уже привязана для всех устаревших решений политики активации CLR версии 2 (например, с помощью атрибута `useLegacyV2RuntimeActivationPolicy` в [элементе\<startup >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) в файле конфигурации), этот метод не возвращает результат ошибки. Вместо этого результатом будет значение S_OK, точно так же, как если бы метод успешно привязать устаревшую политику активации.</span><span class="sxs-lookup"><span data-stu-id="55e3c-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e3c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="55e3c-115">Requirements</span></span>  
 <span data-ttu-id="55e3c-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55e3c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e3c-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="55e3c-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="55e3c-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55e3c-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e3c-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e3c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e3c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="55e3c-120">See also</span></span>

- [<span data-ttu-id="55e3c-121">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="55e3c-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="55e3c-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="55e3c-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="55e3c-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="55e3c-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="55e3c-124">Элемент \<startup></span><span class="sxs-lookup"><span data-stu-id="55e3c-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
