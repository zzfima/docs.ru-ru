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
ms.openlocfilehash: dffefedf14d5f219736e429be191021b2de7ddd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125597"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="693f3-102">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="693f3-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="693f3-103">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="693f3-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="693f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="693f3-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="693f3-105">Участники</span><span class="sxs-lookup"><span data-stu-id="693f3-105">Members</span></span>  
  
|<span data-ttu-id="693f3-106">Участники</span><span class="sxs-lookup"><span data-stu-id="693f3-106">Members</span></span>|<span data-ttu-id="693f3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="693f3-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="693f3-108">Начальный адрес блока.</span><span class="sxs-lookup"><span data-stu-id="693f3-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="693f3-109">Длина непрерывного блока.</span><span class="sxs-lookup"><span data-stu-id="693f3-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="693f3-110">Требования</span><span class="sxs-lookup"><span data-stu-id="693f3-110">Requirements</span></span>  
 <span data-ttu-id="693f3-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="693f3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="693f3-112">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="693f3-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="693f3-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="693f3-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="693f3-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="693f3-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="693f3-115">См. также</span><span class="sxs-lookup"><span data-stu-id="693f3-115">See also</span></span>

- [<span data-ttu-id="693f3-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="693f3-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
