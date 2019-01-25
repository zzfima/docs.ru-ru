---
title: Структура COR_PRF_FUNCTION_ARGUMENT_RANGE
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ddd8e86b119a3c19417306dee056e435a4f5d07a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537911"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="e28e8-102">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="e28e8-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="e28e8-103">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="e28e8-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e28e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e28e8-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="e28e8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e28e8-105">Members</span></span>  
  
|<span data-ttu-id="e28e8-106">Участники</span><span class="sxs-lookup"><span data-stu-id="e28e8-106">Members</span></span>|<span data-ttu-id="e28e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e28e8-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="e28e8-108">Начальный адрес блока.</span><span class="sxs-lookup"><span data-stu-id="e28e8-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="e28e8-109">Длина непрерывного блока.</span><span class="sxs-lookup"><span data-stu-id="e28e8-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e28e8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e28e8-110">Requirements</span></span>  
 <span data-ttu-id="e28e8-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e28e8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e28e8-112">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="e28e8-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="e28e8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e28e8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e28e8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e28e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28e8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e28e8-115">See also</span></span>
- [<span data-ttu-id="e28e8-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="e28e8-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
