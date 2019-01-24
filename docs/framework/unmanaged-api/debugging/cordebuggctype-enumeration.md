---
title: Перечисление CorDebugGCType
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e08a486089a5697b9b3bb4b52c69fda3b661a6ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654754"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="e88a3-102">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="e88a3-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="e88a3-103">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="e88a3-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e88a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e88a3-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e88a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e88a3-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="e88a3-106">Участники</span><span class="sxs-lookup"><span data-stu-id="e88a3-106">Members</span></span>  
  
|<span data-ttu-id="e88a3-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="e88a3-107">Member name</span></span>|<span data-ttu-id="e88a3-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="e88a3-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="e88a3-109">Сборщик мусора работает на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="e88a3-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="e88a3-110">Сборщик мусора работает на сервере.</span><span class="sxs-lookup"><span data-stu-id="e88a3-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e88a3-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="e88a3-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e88a3-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e88a3-112">Requirements</span></span>  
 <span data-ttu-id="e88a3-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e88a3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e88a3-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e88a3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e88a3-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e88a3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e88a3-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e88a3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88a3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e88a3-117">See also</span></span>
- [<span data-ttu-id="e88a3-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="e88a3-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
