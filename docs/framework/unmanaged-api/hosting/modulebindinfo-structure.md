---
title: "Структура ModuleBindInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ModuleBindInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: ModuleBindInfo
helpviewer_keywords: ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 399ba2471b4dc7c5e372a56a9dcab8117068a693
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="4e477-102">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="4e477-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="4e477-103">Предоставляет подробные сведения о модуле, на который указывает ссылка и сборки, содержащей его.</span><span class="sxs-lookup"><span data-stu-id="4e477-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e477-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e477-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="4e477-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4e477-105">Members</span></span>  
  
|<span data-ttu-id="4e477-106">Член</span><span class="sxs-lookup"><span data-stu-id="4e477-106">Member</span></span>|<span data-ttu-id="4e477-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="4e477-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="4e477-108">Уникальный идентификатор для `IStream` , возвращается путем вызова [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) метода, из которого производится загрузка модуля.</span><span class="sxs-lookup"><span data-stu-id="4e477-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="4e477-109">Уникальный идентификатор сборки, содержащей модуль, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="4e477-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="4e477-110">Имя модуля, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="4e477-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e477-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4e477-111">Remarks</span></span>  
 <span data-ttu-id="4e477-112">`ModuleBindInfo`передается в качестве параметра `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="4e477-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="4e477-113">Узел предоставляет уникальный идентификатор `dwAppDomainId` для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="4e477-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="4e477-114">После вызова [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) метод возвращает управление, среда выполнения использует идентификатор, чтобы определить, является ли содержимое `IStream` были сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="4e477-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="4e477-115">В этом случае среда выполнения загружает имеющуюся копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="4e477-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="4e477-116">Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов `IHostAssemblyStore::ProvideAssembly` метод.</span><span class="sxs-lookup"><span data-stu-id="4e477-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="4e477-117">Таким образом идентификатор должен быть уникальным для запросов модулей также и для запросов сборок.</span><span class="sxs-lookup"><span data-stu-id="4e477-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e477-118">Требования</span><span class="sxs-lookup"><span data-stu-id="4e477-118">Requirements</span></span>  
 <span data-ttu-id="4e477-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e477-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e477-120">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="4e477-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4e477-121">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e477-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e477-122">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e477-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e477-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4e477-123">See Also</span></span>  
 [<span data-ttu-id="4e477-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="4e477-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="4e477-125">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="4e477-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 [<span data-ttu-id="4e477-126">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4e477-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="4e477-127">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4e477-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="4e477-128">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="4e477-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
