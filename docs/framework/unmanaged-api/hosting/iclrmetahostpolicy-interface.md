---
title: "Интерфейс ICLRMetaHostPolicy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy
helpviewer_keywords: ICLRMetaHostPolicy interface [.NET Framework hosting]
ms.assetid: 1bdeccb6-0698-4c97-ad69-eae2b69e59f1
topic_type: apiref
caps.latest.revision: "23"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b8cbe1d397e1214cfa4d3f4cbc3d6cdf2d3ccd5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="5b80b-102">Интерфейс ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="5b80b-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="5b80b-103">Предоставляет [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) метод, который возвращает указатель на общий интерфейс языка среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5b80b-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b80b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5b80b-104">Methods</span></span>  
  
|<span data-ttu-id="5b80b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5b80b-105">Method</span></span>|<span data-ttu-id="5b80b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5b80b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b80b-107">GetRequestedRuntime-метод</span><span class="sxs-lookup"><span data-stu-id="5b80b-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="5b80b-108">Предоставляет основной интерфейс среды CLR на основе критериев политики, управляемой сборки, версии и конфигурации файла.</span><span class="sxs-lookup"><span data-stu-id="5b80b-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b80b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b80b-109">Remarks</span></span>  
 <span data-ttu-id="5b80b-110">Ссылка на этот интерфейс можно получить, вызвав [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) работать так, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="5b80b-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
>  <span data-ttu-id="5b80b-111">Этот интерфейс фактически не загружает и не активирует среды CLR, а просто возвращает предпочтительную версию среды CLR на основе доступных версий установленных или загружен.</span><span class="sxs-lookup"><span data-stu-id="5b80b-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="5b80b-112">[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] API размещения консолидирует политики, чтобы узлы с определенными требованиями могли использовать базовую функциональность без возникновения непреднамеренных издержек.</span><span class="sxs-lookup"><span data-stu-id="5b80b-112">The [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="5b80b-113">Например многие экспорты MSCorEE.dll привязывается к определенной среде CLR, несмотря на то, что метод может логически не требовать этого.</span><span class="sxs-lookup"><span data-stu-id="5b80b-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="5b80b-114">[METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) перечисление предоставляет политики привязки, которые являются общими для большинства узлов.</span><span class="sxs-lookup"><span data-stu-id="5b80b-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b80b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5b80b-115">Requirements</span></span>  
 <span data-ttu-id="5b80b-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b80b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b80b-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5b80b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b80b-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b80b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b80b-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b80b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b80b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5b80b-120">See Also</span></span>  
 [<span data-ttu-id="5b80b-121">Интерфейсы размещения CLR, добавленные в .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="5b80b-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="5b80b-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="5b80b-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="5b80b-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="5b80b-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
