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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196948"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="71f9a-102">Перечисление COR_PRF_GC_REASON</span><span class="sxs-lookup"><span data-stu-id="71f9a-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="71f9a-103">Указывает причину возникновения сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="71f9a-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f9a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71f9a-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="71f9a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="71f9a-105">Members</span></span>  
  
|<span data-ttu-id="71f9a-106">Член</span><span class="sxs-lookup"><span data-stu-id="71f9a-106">Member</span></span>|<span data-ttu-id="71f9a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="71f9a-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="71f9a-108">Сборка мусора была вызвана с <xref:System.GC.Collect%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="71f9a-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="71f9a-109">Причина не задана.</span><span class="sxs-lookup"><span data-stu-id="71f9a-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71f9a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="71f9a-110">Requirements</span></span>  
 <span data-ttu-id="71f9a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71f9a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71f9a-112">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71f9a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71f9a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71f9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71f9a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71f9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f9a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="71f9a-115">See also</span></span>

- [<span data-ttu-id="71f9a-116">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="71f9a-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
