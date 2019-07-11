---
title: Перечисление CorDebugCreateProcessFlags
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0dfc7da632a5e56f0f6ab6ed55d1e722f49c7e88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740293"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="dc6ee-102">Перечисление CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="dc6ee-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="dc6ee-103">Предоставляет дополнительные параметры отладки, которые могут использоваться в вызове [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="dc6ee-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc6ee-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="dc6ee-105">Участники</span><span class="sxs-lookup"><span data-stu-id="dc6ee-105">Members</span></span>  
  
|<span data-ttu-id="dc6ee-106">Член</span><span class="sxs-lookup"><span data-stu-id="dc6ee-106">Member</span></span>|<span data-ttu-id="dc6ee-107">Описание</span><span class="sxs-lookup"><span data-stu-id="dc6ee-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="dc6ee-108">Специальные параметры не заданы.</span><span class="sxs-lookup"><span data-stu-id="dc6ee-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dc6ee-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dc6ee-109">Requirements</span></span>  
 <span data-ttu-id="dc6ee-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6ee-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc6ee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc6ee-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6ee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6ee-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6ee-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dc6ee-114">See also</span></span>

- [<span data-ttu-id="dc6ee-115">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="dc6ee-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
