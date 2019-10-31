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
ms.openlocfilehash: 2493b5338824e1eab3f82a9023bbcced59a98fc8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134465"
---
# <a name="iassemblycacheitem-interface"></a><span data-ttu-id="40ac0-102">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="40ac0-102">IAssemblyCacheItem Interface</span></span>
<span data-ttu-id="40ac0-103">Представляет отдельную сборку в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="40ac0-103">Represents a single assembly in the global assembly cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40ac0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="40ac0-104">Methods</span></span>  
  
|<span data-ttu-id="40ac0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="40ac0-105">Method</span></span>|<span data-ttu-id="40ac0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="40ac0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40ac0-107">Метод AbortItem</span><span class="sxs-lookup"><span data-stu-id="40ac0-107">AbortItem Method</span></span>](iassemblycacheitem-abortitem-method.md)|<span data-ttu-id="40ac0-108">Позволяет сборке в глобальном кэше сборок выполнять операции очистки до ее освобождения.</span><span class="sxs-lookup"><span data-stu-id="40ac0-108">Allows the assembly in the global assembly cache to perform cleanup operations before it is released.</span></span>|  
|[<span data-ttu-id="40ac0-109">Метод Commit</span><span class="sxs-lookup"><span data-stu-id="40ac0-109">Commit Method</span></span>](iassemblycacheitem-commit-method.md)|<span data-ttu-id="40ac0-110">Фиксирует в памяти ссылку на кэшированную сборку.</span><span class="sxs-lookup"><span data-stu-id="40ac0-110">Commits the cached assembly reference to memory.</span></span>|  
|[<span data-ttu-id="40ac0-111">Метод CreateStream</span><span class="sxs-lookup"><span data-stu-id="40ac0-111">CreateStream Method</span></span>](iassemblycacheitem-createstream-method.md)|<span data-ttu-id="40ac0-112">Создает поток с указанными именем и форматом.</span><span class="sxs-lookup"><span data-stu-id="40ac0-112">Creates a stream with the specified name and format.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40ac0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="40ac0-113">Requirements</span></span>  
 <span data-ttu-id="40ac0-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40ac0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ac0-115">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="40ac0-115">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="40ac0-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40ac0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ac0-117">См. также</span><span class="sxs-lookup"><span data-stu-id="40ac0-117">See also</span></span>

- [<span data-ttu-id="40ac0-118">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="40ac0-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="40ac0-119">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="40ac0-119">Global Assembly Cache</span></span>](../../app-domains/gac.md)
- [<span data-ttu-id="40ac0-120">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="40ac0-120">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
