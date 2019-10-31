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
ms.openlocfilehash: b954aa0e4db10fd4b3bde951c7f27d18b8634f5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132184"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="ba83e-102">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="ba83e-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="ba83e-103">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="ba83e-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba83e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba83e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba83e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba83e-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="ba83e-106">Члены</span><span class="sxs-lookup"><span data-stu-id="ba83e-106">Members</span></span>  
  
|<span data-ttu-id="ba83e-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="ba83e-107">Member name</span></span>|<span data-ttu-id="ba83e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ba83e-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="ba83e-109">Сборщик мусора работает на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="ba83e-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="ba83e-110">Сборщик мусора работает на сервере.</span><span class="sxs-lookup"><span data-stu-id="ba83e-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba83e-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="ba83e-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba83e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ba83e-112">Requirements</span></span>  
 <span data-ttu-id="ba83e-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba83e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba83e-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba83e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba83e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba83e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba83e-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba83e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba83e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ba83e-117">See also</span></span>

- [<span data-ttu-id="ba83e-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="ba83e-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
