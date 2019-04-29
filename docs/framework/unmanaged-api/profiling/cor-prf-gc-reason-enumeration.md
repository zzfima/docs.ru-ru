---
title: Перечисление COR_PRF_GC_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf97f25b1adc30b173fcd81812a4b197915cdd1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775054"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="c70fe-102">Перечисление COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="c70fe-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="c70fe-103">Указывает причину возникновения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c70fe-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c70fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c70fe-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="c70fe-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c70fe-105">Members</span></span>  
  
|<span data-ttu-id="c70fe-106">Член</span><span class="sxs-lookup"><span data-stu-id="c70fe-106">Member</span></span>|<span data-ttu-id="c70fe-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c70fe-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="c70fe-108">Сборка мусора была вызвана с <xref:System.GC.Collect%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="c70fe-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="c70fe-109">Причина не задана.</span><span class="sxs-lookup"><span data-stu-id="c70fe-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c70fe-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c70fe-110">Requirements</span></span>  
 <span data-ttu-id="c70fe-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c70fe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c70fe-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c70fe-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c70fe-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c70fe-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c70fe-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c70fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c70fe-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c70fe-115">See also</span></span>

- [<span data-ttu-id="c70fe-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="c70fe-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
