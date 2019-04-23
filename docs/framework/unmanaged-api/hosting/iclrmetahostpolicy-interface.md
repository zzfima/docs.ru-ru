---
title: Интерфейс ICLRMetaHostPolicy
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy
helpviewer_keywords:
- ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93507ac72b79210dc3a267fea39a6a7b2874916a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188575"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="0a637-102">Интерфейс ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="0a637-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="0a637-103">Предоставляет [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод, который возвращает указатель на общий интерфейс языка среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0a637-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a637-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0a637-104">Methods</span></span>  
  
|<span data-ttu-id="0a637-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0a637-105">Method</span></span>|<span data-ttu-id="0a637-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0a637-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a637-107">Метод GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="0a637-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="0a637-108">Предоставляет основной интерфейс среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0a637-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a637-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0a637-109">Remarks</span></span>  
 <span data-ttu-id="0a637-110">Ссылка на этот интерфейс можно получить, вызвав [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) работать так, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="0a637-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="0a637-111">Этот интерфейс не были фактически загрузить или активировать среды CLR, а просто возвращает предпочтительную версию среды CLR на основе доступных версий, установленных или загруженных.</span><span class="sxs-lookup"><span data-stu-id="0a637-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="0a637-112">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] Интерфейс API размещения консолидирует политики, благодаря чему узлы с конкретными потребностями может использовать основные функциональные возможности без возникновения непреднамеренных издержек.</span><span class="sxs-lookup"><span data-stu-id="0a637-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="0a637-113">Например многие из экспортов библиотек MSCorEE.dll привязывается к определенной среде CLR, несмотря на то, что метод может логически не требовать его.</span><span class="sxs-lookup"><span data-stu-id="0a637-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="0a637-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) перечисление предоставляет политики привязки, которые являются общими для большинства узлов.</span><span class="sxs-lookup"><span data-stu-id="0a637-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a637-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0a637-115">Requirements</span></span>  
 <span data-ttu-id="0a637-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a637-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a637-117">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0a637-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0a637-118">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a637-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a637-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a637-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a637-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0a637-120">See also</span></span>

- [<span data-ttu-id="0a637-121">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="0a637-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="0a637-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0a637-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="0a637-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="0a637-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
