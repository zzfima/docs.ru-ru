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
ms.openlocfilehash: 4432b17e5d9aa875d8346b3329cd618e15222040
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771022"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="e1f22-102">Метод IAssemblyCache::CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="e1f22-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="e1f22-103">Получает ссылку на новый [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="e1f22-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f22-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1f22-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1f22-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1f22-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e1f22-106">[in] Флаги, определенные в Fusion.idl.</span><span class="sxs-lookup"><span data-stu-id="e1f22-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="e1f22-107">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="e1f22-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="e1f22-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="e1f22-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="e1f22-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="e1f22-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e1f22-110">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="e1f22-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e1f22-111">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="e1f22-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="e1f22-112">[out] Возвращенный `IAssemblyCacheItem` указатель.</span><span class="sxs-lookup"><span data-stu-id="e1f22-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="e1f22-113">[in, optional] Uncanonicalized, разделенных запятыми `name=value` пары.</span><span class="sxs-lookup"><span data-stu-id="e1f22-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1f22-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e1f22-114">Requirements</span></span>  
 <span data-ttu-id="e1f22-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1f22-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1f22-116">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e1f22-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e1f22-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1f22-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f22-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e1f22-118">See also</span></span>

- [<span data-ttu-id="e1f22-119">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="e1f22-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="e1f22-120">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="e1f22-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
