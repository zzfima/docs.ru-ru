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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f14d3dcaad1cc8cac11599b1647d61df3a793301
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765184"
---
# <a name="modulebindinfo-structure"></a><span data-ttu-id="28e2a-102">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="28e2a-102">ModuleBindInfo Structure</span></span>
<span data-ttu-id="28e2a-103">Предоставляет подробные сведения о модуле, на которые имеются ссылки и сборки, содержащей его.</span><span class="sxs-lookup"><span data-stu-id="28e2a-103">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e2a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28e2a-104">Syntax</span></span>  
  
```  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="28e2a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="28e2a-105">Members</span></span>  
  
|<span data-ttu-id="28e2a-106">Член</span><span class="sxs-lookup"><span data-stu-id="28e2a-106">Member</span></span>|<span data-ttu-id="28e2a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="28e2a-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="28e2a-108">Уникальный идентификатор для `IStream` возвращаемый путем вызова [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) метод, из которого необходимо загрузить модуль, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="28e2a-108">A unique identifier for the `IStream` that is returned by a call to the [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md) method from which the referenced module is to be loaded.</span></span>|  
|`lpAssemblyIdentity`|<span data-ttu-id="28e2a-109">Уникальный идентификатор сборки, содержащей модуль, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="28e2a-109">A unique identifier for the assembly that contains the referenced module.</span></span>|  
|`lpModuleName`|<span data-ttu-id="28e2a-110">Имя модуля, на который указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="28e2a-110">The name of the referenced module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28e2a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="28e2a-111">Remarks</span></span>  
 <span data-ttu-id="28e2a-112">`ModuleBindInfo` передается в качестве параметра `IHostAssemblyStore::ProvideModule`.</span><span class="sxs-lookup"><span data-stu-id="28e2a-112">`ModuleBindInfo` is passed as a parameter to `IHostAssemblyStore::ProvideModule`.</span></span> <span data-ttu-id="28e2a-113">Узел предоставляет уникальный идентификатор `dwAppDomainId` для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="28e2a-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="28e2a-114">После вызова [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) возвращает метод, среда выполнения использует идентификатор для определения ли содержимое `IStream` были сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="28e2a-114">After a call to the [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) method returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="28e2a-115">Если Да, среда выполнения загружает имеющуюся копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="28e2a-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="28e2a-116">Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов `IHostAssemblyStore::ProvideAssembly` метод.</span><span class="sxs-lookup"><span data-stu-id="28e2a-116">The runtime also uses this identifier as a lookup key for streams that are returned from calls to the `IHostAssemblyStore::ProvideAssembly` method.</span></span> <span data-ttu-id="28e2a-117">Таким образом идентификатор должен быть уникальным для запросов модулей, а также и для запросов сборок.</span><span class="sxs-lookup"><span data-stu-id="28e2a-117">Therefore, the identifier must be unique for module requests as well as for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28e2a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="28e2a-118">Requirements</span></span>  
 <span data-ttu-id="28e2a-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28e2a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28e2a-120">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="28e2a-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="28e2a-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28e2a-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28e2a-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28e2a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e2a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="28e2a-123">See also</span></span>

- [<span data-ttu-id="28e2a-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="28e2a-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="28e2a-125">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="28e2a-125">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [<span data-ttu-id="28e2a-126">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="28e2a-126">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="28e2a-127">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="28e2a-127">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="28e2a-128">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="28e2a-128">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
