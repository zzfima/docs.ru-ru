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
ms.openlocfilehash: 40698a49ac7012c4f67eb88b1ead04c80f3dea77
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428326"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="c0ca5-102">Структура COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="c0ca5-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="c0ca5-103">Выдает уникальное представление функции, объединяя ее идентификатор с идентификатором перекомпилированной версии этой функции.</span><span class="sxs-lookup"><span data-stu-id="c0ca5-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ca5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0ca5-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="c0ca5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c0ca5-105">Members</span></span>  
  
|<span data-ttu-id="c0ca5-106">Член</span><span class="sxs-lookup"><span data-stu-id="c0ca5-106">Member</span></span>|<span data-ttu-id="c0ca5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c0ca5-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="c0ca5-108">The ID of the function.</span><span class="sxs-lookup"><span data-stu-id="c0ca5-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="c0ca5-109">The ID of the recompiled function.</span><span class="sxs-lookup"><span data-stu-id="c0ca5-109">The ID of the recompiled function.</span></span> <span data-ttu-id="c0ca5-110">A value of 0 (zero) represents the original version of the function.</span><span class="sxs-lookup"><span data-stu-id="c0ca5-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0ca5-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="c0ca5-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ca5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c0ca5-112">Requirements</span></span>  
 <span data-ttu-id="c0ca5-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ca5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ca5-114">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="c0ca5-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="c0ca5-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ca5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ca5-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ca5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ca5-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c0ca5-117">See also</span></span>

- [<span data-ttu-id="c0ca5-118">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="c0ca5-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
