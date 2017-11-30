---
title: "Перечисление COR_GC_THREAD_STATS_TYPES"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_THREAD_STATS_TYPES
api_location: mscoree.dll
api_type: COM
f1_keywords: COR_GC_THREAD_STATS_TYPES
helpviewer_keywords: COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85dc7a1954793efa7a39bec70bdda92a5537b770
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corgcthreadstatstypes-enumeration"></a><span data-ttu-id="e7088-102">Перечисление COR_GC_THREAD_STATS_TYPES</span><span class="sxs-lookup"><span data-stu-id="e7088-102">COR_GC_THREAD_STATS_TYPES Enumeration</span></span>
<span data-ttu-id="e7088-103">Указывает статистику сборки мусора для потока.</span><span class="sxs-lookup"><span data-stu-id="e7088-103">Indicates the garbage collection statistics for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7088-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7088-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a><span data-ttu-id="e7088-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e7088-105">Members</span></span>  
  
|<span data-ttu-id="e7088-106">Член</span><span class="sxs-lookup"><span data-stu-id="e7088-106">Member</span></span>|<span data-ttu-id="e7088-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e7088-107">Description</span></span>|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|<span data-ttu-id="e7088-108">Поток имеет байт, которые были переданы в последнюю сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="e7088-108">The thread has bytes that were promoted in the most recent garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7088-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e7088-109">Requirements</span></span>  
 <span data-ttu-id="e7088-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7088-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7088-111">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="e7088-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="e7088-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7088-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7088-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e7088-113">See Also</span></span>  
 [<span data-ttu-id="e7088-114">Перечисления размещения</span><span class="sxs-lookup"><span data-stu-id="e7088-114">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
