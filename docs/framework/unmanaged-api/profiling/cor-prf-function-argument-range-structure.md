---
title: "Структура COR_PRF_FUNCTION_ARGUMENT_RANGE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f61d23fc3ee3c6c8adb46c0deecdd72d155ae65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="f5a1c-102">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="f5a1c-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="f5a1c-103">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="f5a1c-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5a1c-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="f5a1c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f5a1c-105">Members</span></span>  
  
|<span data-ttu-id="f5a1c-106">Участники</span><span class="sxs-lookup"><span data-stu-id="f5a1c-106">Members</span></span>|<span data-ttu-id="f5a1c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f5a1c-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="f5a1c-108">Начальный адрес блока.</span><span class="sxs-lookup"><span data-stu-id="f5a1c-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="f5a1c-109">Длина непрерывного блока.</span><span class="sxs-lookup"><span data-stu-id="f5a1c-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5a1c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f5a1c-110">Requirements</span></span>  
 <span data-ttu-id="f5a1c-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a1c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a1c-112">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="f5a1c-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="f5a1c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a1c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a1c-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a1c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a1c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f5a1c-115">See Also</span></span>  
 [<span data-ttu-id="f5a1c-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="f5a1c-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
