---
title: Перечисление CorDebugGenerationTypes
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 362e917e1684c91bde80a8b5c2e6a27a18a99190
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098199"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="54520-102">Перечисление CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="54520-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="54520-103">Указывает на создание области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="54520-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54520-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54520-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="54520-105">Члены</span><span class="sxs-lookup"><span data-stu-id="54520-105">Members</span></span>  
  
|<span data-ttu-id="54520-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="54520-106">Member name</span></span>|<span data-ttu-id="54520-107">Описание</span><span class="sxs-lookup"><span data-stu-id="54520-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="54520-108">Поколение 0.</span><span class="sxs-lookup"><span data-stu-id="54520-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="54520-109">Поколение 1.</span><span class="sxs-lookup"><span data-stu-id="54520-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="54520-110">Поколение 2.</span><span class="sxs-lookup"><span data-stu-id="54520-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="54520-111">Куча больших объектов.</span><span class="sxs-lookup"><span data-stu-id="54520-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54520-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="54520-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54520-113">Требования</span><span class="sxs-lookup"><span data-stu-id="54520-113">Requirements</span></span>  
 <span data-ttu-id="54520-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54520-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54520-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54520-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54520-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54520-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54520-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54520-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54520-118">См. также</span><span class="sxs-lookup"><span data-stu-id="54520-118">See also</span></span>

- [<span data-ttu-id="54520-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="54520-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
