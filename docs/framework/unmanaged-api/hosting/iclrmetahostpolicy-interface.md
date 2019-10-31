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
ms.openlocfilehash: 277c13895374116eb67f6515f45df638f61b0453
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140855"
---
# <a name="iclrmetahostpolicy-interface"></a><span data-ttu-id="e19cc-102">Интерфейс ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="e19cc-102">ICLRMetaHostPolicy Interface</span></span>
<span data-ttu-id="e19cc-103">Предоставляет метод [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , возвращающий указатель на интерфейс среды CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e19cc-103">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, which returns a pointer to a common language runtime (CLR) interface based on a policy criteria, managed assembly, version and configuration file.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e19cc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e19cc-104">Methods</span></span>  
  
|<span data-ttu-id="e19cc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e19cc-105">Method</span></span>|<span data-ttu-id="e19cc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e19cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e19cc-107">Метод GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="e19cc-107">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)|<span data-ttu-id="e19cc-108">Предоставляет предпочтительный интерфейс CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e19cc-108">Provides a preferred CLR interface based on a policy criteria, managed assembly, version, and configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e19cc-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="e19cc-109">Remarks</span></span>  
 <span data-ttu-id="e19cc-110">Ссылку на этот интерфейс можно получить, вызвав функцию [клркреатеинстанце](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) , как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="e19cc-110">You can get a reference to this interface by calling the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function as shown in the following code:</span></span>  
  
```cpp  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHostPolicy,  
                   IID_ICLRMetaHostPolicy, (LPVOID*)&pMetaHostPolicy);  
```  
  
> [!NOTE]
> <span data-ttu-id="e19cc-111">Этот интерфейс фактически не загружает и не активирует среду CLR, а просто возвращает предпочтительную версию среды CLR на основе установленных или загруженных версий.</span><span class="sxs-lookup"><span data-stu-id="e19cc-111">This interface does not actually load or activate the CLR, but simply returns the preferred CLR version based on the available versions that are installed or loaded.</span></span>  
  
 <span data-ttu-id="e19cc-112">В .NET Framework 4 API размещения консолидируются политики, чтобы узлы с конкретными потребностями могли использовать базовые функции без непреднамеренной потерь.</span><span class="sxs-lookup"><span data-stu-id="e19cc-112">The .NET Framework 4 hosting API consolidates policies so that hosts with specific needs may use basic functionality without incurring unintended penalties.</span></span> <span data-ttu-id="e19cc-113">Например, многие экспорты MSCorEE. dll привязываются к определенной среде CLR, хотя метод может не потребовать его логически.</span><span class="sxs-lookup"><span data-stu-id="e19cc-113">For example, many of the MSCorEE.dll exports will bind to a specific CLR, although a method might not logically require it.</span></span> <span data-ttu-id="e19cc-114">Перечисление [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) предоставляет политики привязки, общие для большинства узлов.</span><span class="sxs-lookup"><span data-stu-id="e19cc-114">The [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeration provides binding policies that are common to the majority of hosts.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e19cc-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e19cc-115">Requirements</span></span>  
 <span data-ttu-id="e19cc-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e19cc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e19cc-117">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="e19cc-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e19cc-118">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e19cc-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e19cc-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e19cc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e19cc-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e19cc-120">See also</span></span>

- [<span data-ttu-id="e19cc-121">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="e19cc-121">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="e19cc-122">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="e19cc-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="e19cc-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="e19cc-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
