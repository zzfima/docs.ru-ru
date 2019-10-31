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
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192110"
---
# <a name="assemblybindinfo-structure"></a><span data-ttu-id="572c5-102">Структура AssemblyBindInfo</span><span class="sxs-lookup"><span data-stu-id="572c5-102">AssemblyBindInfo Structure</span></span>
<span data-ttu-id="572c5-103">Предоставляет подробные сведения о сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="572c5-103">Provides detailed information about the referenced assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572c5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="572c5-104">Syntax</span></span>  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="572c5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="572c5-105">Members</span></span>  
  
|<span data-ttu-id="572c5-106">Член</span><span class="sxs-lookup"><span data-stu-id="572c5-106">Member</span></span>|<span data-ttu-id="572c5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="572c5-107">Description</span></span>|  
|------------|-----------------|  
|`dwAppDomainId`|<span data-ttu-id="572c5-108">Уникальный идентификатор `IStream`, возвращаемого вызовом метода [IHostAssemblyStore::P ровидеассембли](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), из которого загружается сборка, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="572c5-108">A unique identifier for the `IStream` returned by a call to [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md), from which the referenced assembly is to be loaded.</span></span>|  
|`lpReferencedIdentity`|<span data-ttu-id="572c5-109">Уникальный идентификатор сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="572c5-109">A unique identifier for the referenced assembly.</span></span>|  
|`lpPostPolicyIdentity`|<span data-ttu-id="572c5-110">Идентификатор сборки, на которую указывает ссылка, после применения любых значений политики привязки.</span><span class="sxs-lookup"><span data-stu-id="572c5-110">The identifier for the referenced assembly after the application of any binding policy values.</span></span>|  
|`ePolicyLevel`|<span data-ttu-id="572c5-111">Одно из значений [еполициактион](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) , указывающее, какие политики управления версиями должны применяться к сборке, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="572c5-111">One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that indicate which versioning policies, if any, should be applied to the referenced assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="572c5-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="572c5-112">Remarks</span></span>  
 <span data-ttu-id="572c5-113">Узел предоставляет уникальный идентификатор, `dwAppDomainId` общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="572c5-113">The host supplies the unique identifier `dwAppDomainId` to the common language runtime (CLR).</span></span> <span data-ttu-id="572c5-114">После того как вызов `IHostAssemblyStore::ProvideAssembly` возвращает, среда выполнения использует идентификатор, чтобы определить, сопоставлено ли содержимое `IStream`.</span><span class="sxs-lookup"><span data-stu-id="572c5-114">After a call to `IHostAssemblyStore::ProvideAssembly` returns, the runtime uses the identifier to determine whether the contents of the `IStream` have been mapped.</span></span> <span data-ttu-id="572c5-115">Если это так, среда выполнения загружает существующую копию вместо повторного сопоставления потока.</span><span class="sxs-lookup"><span data-stu-id="572c5-115">If so, the runtime loads the existing copy rather than remapping the stream.</span></span> <span data-ttu-id="572c5-116">Среда выполнения также использует этот идентификатор в качестве ключа поиска для потоков, возвращаемых из вызовов [IHostAssemblyStore::P ровидемодуле](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span><span class="sxs-lookup"><span data-stu-id="572c5-116">The runtime also uses this identifier as a lookup key for streams returned from calls to [IHostAssemblyStore::ProvideModule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md).</span></span> <span data-ttu-id="572c5-117">Таким образом, идентификатор должен быть уникальным для запросов модуля и для запросов сборки.</span><span class="sxs-lookup"><span data-stu-id="572c5-117">Therefore, the identifier must be unique for module requests and for assembly requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="572c5-118">Требования</span><span class="sxs-lookup"><span data-stu-id="572c5-118">Requirements</span></span>  
 <span data-ttu-id="572c5-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="572c5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572c5-120">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="572c5-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="572c5-121">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="572c5-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="572c5-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572c5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572c5-123">См. также</span><span class="sxs-lookup"><span data-stu-id="572c5-123">See also</span></span>

- [<span data-ttu-id="572c5-124">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="572c5-124">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="572c5-125">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="572c5-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="572c5-126">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="572c5-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="572c5-127">Интерфейс IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="572c5-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="572c5-128">Интерфейс IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="572c5-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="572c5-129">Структура ModuleBindInfo</span><span class="sxs-lookup"><span data-stu-id="572c5-129">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
