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
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789362"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="3b14f-102">Перечисление CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="3b14f-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="3b14f-103">Указывает, где выполняется сборщик мусора: на рабочей станции или на сервере.</span><span class="sxs-lookup"><span data-stu-id="3b14f-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b14f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b14f-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b14f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b14f-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="3b14f-106">Участники</span><span class="sxs-lookup"><span data-stu-id="3b14f-106">Members</span></span>  
  
|<span data-ttu-id="3b14f-107">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="3b14f-107">Member name</span></span>|<span data-ttu-id="3b14f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="3b14f-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="3b14f-109">Сборщик мусора работает на рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="3b14f-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="3b14f-110">Сборщик мусора работает на сервере.</span><span class="sxs-lookup"><span data-stu-id="3b14f-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b14f-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="3b14f-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b14f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3b14f-112">Requirements</span></span>  
 <span data-ttu-id="3b14f-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b14f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b14f-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b14f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b14f-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b14f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b14f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b14f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b14f-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b14f-117">See also</span></span>

- [<span data-ttu-id="3b14f-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="3b14f-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
