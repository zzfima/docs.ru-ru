---
title: Интерфейс IAssemblyCache
ms.date: 03/30/2017
api_name:
- IAssemblyCache
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache
helpviewer_keywords:
- IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type:
- apiref
ms.openlocfilehash: 5ed0075da1429c70900750f3f28e8ce36a41fb28
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134540"
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="a2cf5-102">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="a2cf5-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="a2cf5-103">Представляет глобальный кэш сборок для использования технологией Fusion.</span><span class="sxs-lookup"><span data-stu-id="a2cf5-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2cf5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a2cf5-104">Methods</span></span>  
  
|<span data-ttu-id="a2cf5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a2cf5-105">Method</span></span>|<span data-ttu-id="a2cf5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a2cf5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2cf5-107">Метод CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="a2cf5-107">CreateAssemblyCacheItem Method</span></span>](iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="a2cf5-108">Возвращает ссылку на новый [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a2cf5-108">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="a2cf5-109">Метод CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="a2cf5-109">CreateAssemblyScavenger Method</span></span>](iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="a2cf5-110">Зарезервировано для внутреннего использования технологией Fusion.</span><span class="sxs-lookup"><span data-stu-id="a2cf5-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="a2cf5-111">Метод InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="a2cf5-111">InstallAssembly Method</span></span>](iassemblycache-installassembly-method.md)|<span data-ttu-id="a2cf5-112">Устанавливает указанную сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="a2cf5-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="a2cf5-113">Метод QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="a2cf5-113">QueryAssemblyInfo Method</span></span>](iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="a2cf5-114">Возвращает запрошенные данные о указанной сборке.</span><span class="sxs-lookup"><span data-stu-id="a2cf5-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="a2cf5-115">Метод UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="a2cf5-115">UninstallAssembly Method</span></span>](iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="a2cf5-116">Удаляет указанную сборку из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="a2cf5-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2cf5-117">Требования</span><span class="sxs-lookup"><span data-stu-id="a2cf5-117">Requirements</span></span>  
 <span data-ttu-id="a2cf5-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2cf5-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2cf5-119">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a2cf5-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a2cf5-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2cf5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2cf5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a2cf5-121">See also</span></span>

- [<span data-ttu-id="a2cf5-122">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="a2cf5-122">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="a2cf5-123">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="a2cf5-123">Global Assembly Cache</span></span>](../../app-domains/gac.md)
