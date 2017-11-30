---
title: "Интерфейс IAssemblyCache"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache
helpviewer_keywords: IAssemblyCache interface [.NET Framework fusion]
ms.assetid: 71ea170f-872d-4fc5-81b6-27da1dec9b19
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6244e6c3b0cc88c50cda050a480f5af5b3996b47
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycache-interface"></a><span data-ttu-id="64bc7-102">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="64bc7-102">IAssemblyCache Interface</span></span>
<span data-ttu-id="64bc7-103">Представляет глобальный кэш сборок для использования технологией fusion.</span><span class="sxs-lookup"><span data-stu-id="64bc7-103">Represents the global assembly cache for use by the fusion technology.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64bc7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="64bc7-104">Methods</span></span>  
  
|<span data-ttu-id="64bc7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="64bc7-105">Method</span></span>|<span data-ttu-id="64bc7-106">Описание</span><span class="sxs-lookup"><span data-stu-id="64bc7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64bc7-107">Метод CreateAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="64bc7-107">CreateAssemblyCacheItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblycacheitem-method.md)|<span data-ttu-id="64bc7-108">Возвращает ссылку на новый [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span><span class="sxs-lookup"><span data-stu-id="64bc7-108">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md).</span></span>|  
|[<span data-ttu-id="64bc7-109">Метод CreateAssemblyScavenger</span><span class="sxs-lookup"><span data-stu-id="64bc7-109">CreateAssemblyScavenger Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-createassemblyscavenger-method.md)|<span data-ttu-id="64bc7-110">Зарезервировано для внутреннего использования технологией fusion.</span><span class="sxs-lookup"><span data-stu-id="64bc7-110">Reserved for internal use by the fusion technology.</span></span>|  
|[<span data-ttu-id="64bc7-111">Метод InstallAssembly</span><span class="sxs-lookup"><span data-stu-id="64bc7-111">InstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-installassembly-method.md)|<span data-ttu-id="64bc7-112">Устанавливает указанную сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="64bc7-112">Installs the specified assembly in the global assembly cache.</span></span>|  
|[<span data-ttu-id="64bc7-113">Метод QueryAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="64bc7-113">QueryAssemblyInfo Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-queryassemblyinfo-method.md)|<span data-ttu-id="64bc7-114">Возвращает запрашиваемые данные об указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="64bc7-114">Gets the requested data about the specified assembly.</span></span>|  
|[<span data-ttu-id="64bc7-115">Метод UninstallAssembly</span><span class="sxs-lookup"><span data-stu-id="64bc7-115">UninstallAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-uninstallassembly-method.md)|<span data-ttu-id="64bc7-116">Удаляет указанную сборку из глобального кэша сборок.</span><span class="sxs-lookup"><span data-stu-id="64bc7-116">Uninstalls the specified assembly from the global assembly cache.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64bc7-117">Требования</span><span class="sxs-lookup"><span data-stu-id="64bc7-117">Requirements</span></span>  
 <span data-ttu-id="64bc7-118">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64bc7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64bc7-119">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="64bc7-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="64bc7-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64bc7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64bc7-121">См. также</span><span class="sxs-lookup"><span data-stu-id="64bc7-121">See Also</span></span>  
 [<span data-ttu-id="64bc7-122">Фьюжн-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="64bc7-122">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="64bc7-123">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="64bc7-123">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
