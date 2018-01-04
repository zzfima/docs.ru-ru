---
title: "Перечисление COR_PRF_GC_REASON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_REASON
helpviewer_keywords: COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75baeddd9c27dec6f110d461268ed546c167fc44
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="92966-102">Перечисление COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="92966-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="92966-103">Указывает причину возникновения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="92966-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92966-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="92966-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="92966-105">Участники</span><span class="sxs-lookup"><span data-stu-id="92966-105">Members</span></span>  
  
|<span data-ttu-id="92966-106">Член</span><span class="sxs-lookup"><span data-stu-id="92966-106">Member</span></span>|<span data-ttu-id="92966-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="92966-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="92966-108">Сборка мусора была вызвана с <xref:System.GC.Collect%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="92966-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="92966-109">Причина не задана.</span><span class="sxs-lookup"><span data-stu-id="92966-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92966-110">Требования</span><span class="sxs-lookup"><span data-stu-id="92966-110">Requirements</span></span>  
 <span data-ttu-id="92966-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92966-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92966-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92966-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92966-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92966-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92966-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92966-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92966-115">См. также</span><span class="sxs-lookup"><span data-stu-id="92966-115">See Also</span></span>  
 [<span data-ttu-id="92966-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="92966-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
