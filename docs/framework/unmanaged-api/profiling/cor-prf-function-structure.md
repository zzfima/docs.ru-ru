---
title: Структура COR_PRF_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14d42a4032c3e2b1c231414678912e1658e759d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775015"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="7a062-102">Структура COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="7a062-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="7a062-103">Выдает уникальное представление функции, объединяя ее идентификатор с идентификатором перекомпилированной версии этой функции.</span><span class="sxs-lookup"><span data-stu-id="7a062-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a062-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a062-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="7a062-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7a062-105">Members</span></span>  
  
|<span data-ttu-id="7a062-106">Член</span><span class="sxs-lookup"><span data-stu-id="7a062-106">Member</span></span>|<span data-ttu-id="7a062-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7a062-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="7a062-108">Идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="7a062-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="7a062-109">Идентификатор перекомпилированной функции.</span><span class="sxs-lookup"><span data-stu-id="7a062-109">The ID of the recompiled function.</span></span> <span data-ttu-id="7a062-110">Значение 0 (ноль) представляет исходную версию функции.</span><span class="sxs-lookup"><span data-stu-id="7a062-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a062-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a062-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a062-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7a062-112">Requirements</span></span>  
 <span data-ttu-id="7a062-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a062-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a062-114">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7a062-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7a062-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a062-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a062-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a062-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a062-117">См. также</span><span class="sxs-lookup"><span data-stu-id="7a062-117">See also</span></span>

- [<span data-ttu-id="7a062-118">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="7a062-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
