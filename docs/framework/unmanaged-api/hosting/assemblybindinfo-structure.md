---
title: Структура AssemblyBindInfo
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce79987c7fcf45b8d10dcc4613e053ee735941de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946852"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="5c2b4-102">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="5c2b4-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="5c2b4-103">Содержит подробные сведения о сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c2b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c2b4-104">Syntax</span></span>  
  
```  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="5c2b4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5c2b4-105">Members</span></span>  
  
|<span data-ttu-id="5c2b4-106">Член</span><span class="sxs-lookup"><span data-stu-id="5c2b4-106">Member</span></span>|<span data-ttu-id="5c2b4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5c2b4-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="5c2b4-108">Уникальный идентификатор для `IStream` возвращается путем вызова [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), из которой сборка будет необходимо загрузить.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="5c2b4-109">Уникальный идентификатор для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="5c2b4-110">Идентификатор указанной ссылками сборки после применения всех значений политики привязки.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="5c2b4-111">Один из [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) значения, указывающие, какие политики управления версиями, если таковые имеются, применяются к указанной ссылками сборки.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c2b4-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="5c2b4-112">Remarks</span></span>  
 <span data-ttu-id="5c2b4-113">Узел предоставляет уникальный идентификатор `dwAppDomainId` для общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="5c2b4-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="5c2b4-114">После вызова `IHostAssemblyStore::ProvideAssembly` возвращает, среда выполнения использует идентификатор для определения ли содержимое `IStream` были сопоставлены.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="5c2b4-115">Если Да, среда выполнения загружает имеющуюся копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="5c2b4-116">Среда выполнения также использует этот идентификатор ключа поиска для потоков, возвращаемых из вызовов [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="5c2b4-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="5c2b4-117">Таким образом идентификатор должен быть уникальным для запросов модулей и запросов сборок.</span><span class="sxs-lookup"><span data-stu-id="5c2b4-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c2b4-118">Требования</span><span class="sxs-lookup"><span data-stu-id="5c2b4-118">Requirements</span></span>  
 <span data-ttu-id="5c2b4-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c2b4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c2b4-120">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5c2b4-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5c2b4-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c2b4-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c2b4-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c2b4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c2b4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="5c2b4-123">See also</span></span>

- [<span data-ttu-id="5c2b4-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="5c2b4-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="5c2b4-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="5c2b4-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5c2b4-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="5c2b4-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5c2b4-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="5c2b4-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="5c2b4-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="5c2b4-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="5c2b4-129">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="5c2b4-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
