---
title: Интерфейс IAssemblyCacheItem
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: ccc9387a-9f44-4f4f-bf8f-0ea6d2afa21b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fba17a2ffad9220acdbc79726efe0d3d4184978a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188556"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="96c8b-102">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="96c8b-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="96c8b-103">Представляет одну сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="96c8b-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="96c8b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="96c8b-104">Methods</span></span>  
  
|<span data-ttu-id="96c8b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="96c8b-105">Method</span></span>|<span data-ttu-id="96c8b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="96c8b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="96c8b-107">Метод AbortItem</span><span class="sxs-lookup"><span data-stu-id="96c8b-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="96c8b-108">Позволяет сборку в глобальный кэш сборок для выполнения операции очистки, перед выпуском.</span><span class="sxs-lookup"><span data-stu-id="96c8b-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="96c8b-109">Метод Commit</span><span class="sxs-lookup"><span data-stu-id="96c8b-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="96c8b-110">Фиксирует ссылки на сборку, кэшированных в памяти.</span><span class="sxs-lookup"><span data-stu-id="96c8b-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="96c8b-111">Метод CreateStream</span><span class="sxs-lookup"><span data-stu-id="96c8b-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="96c8b-112">Создает поток с указанным именем и формат.</span><span class="sxs-lookup"><span data-stu-id="96c8b-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96c8b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="96c8b-113">Requirements</span></span>  
 <span data-ttu-id="96c8b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96c8b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96c8b-115">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="96c8b-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="96c8b-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96c8b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c8b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="96c8b-117">See also</span></span>

- [<span data-ttu-id="96c8b-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="96c8b-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="96c8b-119">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="96c8b-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
- [<span data-ttu-id="96c8b-120">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="96c8b-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
