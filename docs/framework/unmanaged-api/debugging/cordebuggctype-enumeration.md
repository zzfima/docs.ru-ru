---
title: "Перечисление CorDebugGCType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugGCType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGCType
helpviewer_keywords: CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 14d6f28c2e5fa356c7f406ffb4c2787f0ace500a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="25f9d-102">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="25f9d-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="25f9d-103">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="25f9d-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25f9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25f9d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25f9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="25f9d-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="25f9d-106">Члены</span><span class="sxs-lookup"><span data-stu-id="25f9d-106">Members</span></span>  
  
|<span data-ttu-id="25f9d-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="25f9d-107">Member name</span></span>|<span data-ttu-id="25f9d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="25f9d-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="25f9d-109">Сборщик мусора работает на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="25f9d-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="25f9d-110">Сборщик мусора работает на сервере.</span><span class="sxs-lookup"><span data-stu-id="25f9d-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25f9d-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="25f9d-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25f9d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="25f9d-112">Requirements</span></span>  
 <span data-ttu-id="25f9d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25f9d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25f9d-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25f9d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25f9d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25f9d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25f9d-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25f9d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f9d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="25f9d-117">See Also</span></span>  
 [<span data-ttu-id="25f9d-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="25f9d-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
