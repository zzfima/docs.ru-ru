---
title: Метод IAssemblyCache::CreateAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27001f8560dcd128b5d737ed0f219387be86d6e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672312"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="6aca9-102">Метод IAssemblyCache::CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="6aca9-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="6aca9-103">Получает ссылку на новый [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="6aca9-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aca9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aca9-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6aca9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6aca9-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="6aca9-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="6aca9-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="6aca9-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="6aca9-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="6aca9-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="6aca9-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="6aca9-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="6aca9-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="6aca9-110">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="6aca9-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="6aca9-111">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="6aca9-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="6aca9-112">[out] Возвращенный `IAssemblyCacheItem` указатель.</span><span class="sxs-lookup"><span data-stu-id="6aca9-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="6aca9-113">[in, optional] Uncanonicalized, разделенных запятыми `name=value` пары.</span><span class="sxs-lookup"><span data-stu-id="6aca9-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aca9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6aca9-114">Requirements</span></span>  
 <span data-ttu-id="6aca9-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aca9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aca9-116">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6aca9-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6aca9-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aca9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aca9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6aca9-118">See also</span></span>
- [<span data-ttu-id="6aca9-119">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="6aca9-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="6aca9-120">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="6aca9-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
