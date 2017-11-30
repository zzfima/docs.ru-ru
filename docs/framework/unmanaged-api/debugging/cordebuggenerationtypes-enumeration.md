---
title: "Перечисление CorDebugGenerationTypes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGenerationTypes
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGenerationTypes
helpviewer_keywords: CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: adefc0de4ba09419660c214df75365c90ec2c66e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="38e6c-102">Перечисление CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="38e6c-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="38e6c-103">Указывает на создание области памяти в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="38e6c-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e6c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38e6c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="38e6c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="38e6c-105">Members</span></span>  
  
|<span data-ttu-id="38e6c-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="38e6c-106">Member name</span></span>|<span data-ttu-id="38e6c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="38e6c-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="38e6c-108">Поколение 0.</span><span class="sxs-lookup"><span data-stu-id="38e6c-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="38e6c-109">Поколение 1.</span><span class="sxs-lookup"><span data-stu-id="38e6c-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="38e6c-110">Поколение 2.</span><span class="sxs-lookup"><span data-stu-id="38e6c-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="38e6c-111">Для кучи больших объектов.</span><span class="sxs-lookup"><span data-stu-id="38e6c-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38e6c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="38e6c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e6c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="38e6c-113">Requirements</span></span>  
 <span data-ttu-id="38e6c-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e6c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e6c-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38e6c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38e6c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38e6c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38e6c-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e6c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e6c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="38e6c-118">See Also</span></span>  
 [<span data-ttu-id="38e6c-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="38e6c-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
