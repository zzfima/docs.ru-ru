---
title: Структура ModuleBindInfo
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133752"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="d9439-102">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="d9439-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="d9439-103">Предоставляет подробные сведения о модуле, на который указывает ссылка, и содержащей его сборку.</span><span class="sxs-lookup"><span data-stu-id="d9439-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9439-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9439-104">Syntax</span></span>  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="d9439-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d9439-105">Members</span></span>  
  
|<span data-ttu-id="d9439-106">Член</span><span class="sxs-lookup"><span data-stu-id="d9439-106">Member</span></span>|<span data-ttu-id="d9439-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d9439-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="d9439-108">Уникальный идентификатор `IStream`, возвращаемый вызовом метода [IHostAssemblyStore::P ровидемодуле](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) , из которого загружается указанный модуль.</span><span class="sxs-lookup"><span data-stu-id="d9439-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="d9439-109">Уникальный идентификатор сборки, содержащей упоминаемый модуль.</span><span class="sxs-lookup"><span data-stu-id="d9439-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="d9439-110">Имя модуля, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="d9439-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9439-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="d9439-111">Remarks</span></span>  
 <span data-ttu-id="d9439-112">`ModuleBindInfo` передается в качестве параметра `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="d9439-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="d9439-113">Узел предоставляет уникальный идентификатор, `dwAppDomainId` общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="d9439-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="d9439-114">После вызова метода [IHostAssemblyStore::P ровидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) среда выполнения использует идентификатор, чтобы определить, сопоставлено ли содержимое `IStream`.</span><span class="sxs-lookup"><span data-stu-id="d9439-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="d9439-115">Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="d9439-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="d9439-116">Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов метода `IHostAssemblyStore::ProvideAssembly`.</span><span class="sxs-lookup"><span data-stu-id="d9439-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="d9439-117">Таким образом, идентификатор должен быть уникальным для запросов модуля, а также для запросов сборки.</span><span class="sxs-lookup"><span data-stu-id="d9439-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9439-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d9439-118">Requirements</span></span>  
 <span data-ttu-id="d9439-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9439-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9439-120">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="d9439-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d9439-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9439-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9439-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9439-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9439-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d9439-123">See also</span></span>

- [<span data-ttu-id="d9439-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="d9439-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="d9439-125">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="d9439-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="d9439-126">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="d9439-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="d9439-127">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="d9439-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d9439-128">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="d9439-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
