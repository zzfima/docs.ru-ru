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
ms.openlocfilehash: ec33e55f840fe735091364ebc35cb7b7c165c10a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867193"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="2a208-102">Перечисление COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="2a208-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="2a208-103">Указывает причину возникновения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="2a208-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a208-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a208-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="2a208-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2a208-105">Members</span></span>  
  
|<span data-ttu-id="2a208-106">Член</span><span class="sxs-lookup"><span data-stu-id="2a208-106">Member</span></span>|<span data-ttu-id="2a208-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2a208-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="2a208-108">Сборка мусора была вызвана методом <xref:System.GC.Collect%2A>.</span><span class="sxs-lookup"><span data-stu-id="2a208-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="2a208-109">Причина не указана.</span><span class="sxs-lookup"><span data-stu-id="2a208-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a208-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2a208-110">Requirements</span></span>  
 <span data-ttu-id="2a208-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a208-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a208-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a208-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a208-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a208-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a208-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a208-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a208-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a208-115">See also</span></span>

- [<span data-ttu-id="2a208-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="2a208-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
