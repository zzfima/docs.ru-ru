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
ms.openlocfilehash: c0c0679dac84089577a2698ed8b0b5497a1a81e8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753902"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="b0c7a-102">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="b0c7a-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="b0c7a-103">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c7a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0c7a-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="b0c7a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b0c7a-105">Members</span></span>  
  
|<span data-ttu-id="b0c7a-106">Участники</span><span class="sxs-lookup"><span data-stu-id="b0c7a-106">Members</span></span>|<span data-ttu-id="b0c7a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b0c7a-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="b0c7a-108">Начальный адрес блока.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="b0c7a-109">Длина непрерывного блока.</span><span class="sxs-lookup"><span data-stu-id="b0c7a-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0c7a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b0c7a-110">Requirements</span></span>  
 <span data-ttu-id="b0c7a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c7a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c7a-112">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="b0c7a-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b0c7a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0c7a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0c7a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0c7a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c7a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b0c7a-115">See also</span></span>

- [<span data-ttu-id="b0c7a-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="b0c7a-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
