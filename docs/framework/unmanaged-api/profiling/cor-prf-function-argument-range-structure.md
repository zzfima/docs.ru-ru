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
ms.openlocfilehash: 0c0dd9cac695d892c07f33728c22bd35102c4389
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="4f8b9-102">Структура COR_PRF_FUNCTION_ARGUMENT_RANGE</span><span class="sxs-lookup"><span data-stu-id="4f8b9-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="4f8b9-103">Представляет блок аргументов функции, которые сохраняются в памяти последовательно слева направо.</span><span class="sxs-lookup"><span data-stu-id="4f8b9-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f8b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f8b9-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="4f8b9-105">Члены</span><span class="sxs-lookup"><span data-stu-id="4f8b9-105">Members</span></span>  
  
|<span data-ttu-id="4f8b9-106">Члены</span><span class="sxs-lookup"><span data-stu-id="4f8b9-106">Members</span></span>|<span data-ttu-id="4f8b9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4f8b9-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="4f8b9-108">Начальный адрес блока.</span><span class="sxs-lookup"><span data-stu-id="4f8b9-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="4f8b9-109">Длина непрерывного блока.</span><span class="sxs-lookup"><span data-stu-id="4f8b9-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f8b9-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4f8b9-110">Requirements</span></span>  
 <span data-ttu-id="4f8b9-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f8b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f8b9-112">**Заголовок:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="4f8b9-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="4f8b9-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f8b9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f8b9-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f8b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8b9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4f8b9-115">See Also</span></span>  
 [<span data-ttu-id="4f8b9-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="4f8b9-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
