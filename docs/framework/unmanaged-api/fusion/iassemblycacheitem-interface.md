---
title: "Интерфейс IAssemblyCacheItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 323b501efbdf309d5e0d595137407dd8289de17a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="69745-102">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="69745-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="69745-103">Представляет одну сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="69745-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="69745-104">Методы</span><span class="sxs-lookup"><span data-stu-id="69745-104">Methods</span></span>  
  
|<span data-ttu-id="69745-105">Метод</span><span class="sxs-lookup"><span data-stu-id="69745-105">Method</span></span>|<span data-ttu-id="69745-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="69745-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="69745-107">Метод AbortItem</span><span class="sxs-lookup"><span data-stu-id="69745-107">AbortItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="69745-108">Разрешает сборку в глобальный кэш сборок, чтобы выполнить операции очистки, перед выпуском.</span><span class="sxs-lookup"><span data-stu-id="69745-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="69745-109">Метод Commit</span><span class="sxs-lookup"><span data-stu-id="69745-109">Commit Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-commit-method.md)|<span data-ttu-id="69745-110">Фиксирует ссылку на сборку, кэшированных в памяти.</span><span class="sxs-lookup"><span data-stu-id="69745-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="69745-111">Метод CreateStream</span><span class="sxs-lookup"><span data-stu-id="69745-111">CreateStream Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-createstream-method.md)|<span data-ttu-id="69745-112">Создает поток с указанным именем и формат.</span><span class="sxs-lookup"><span data-stu-id="69745-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="69745-113">Требования</span><span class="sxs-lookup"><span data-stu-id="69745-113">Requirements</span></span>  
 <span data-ttu-id="69745-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69745-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69745-115">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="69745-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="69745-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69745-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69745-117">См. также</span><span class="sxs-lookup"><span data-stu-id="69745-117">See Also</span></span>  
 [<span data-ttu-id="69745-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="69745-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="69745-119">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="69745-119">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)  
 [<span data-ttu-id="69745-120">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="69745-120">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
