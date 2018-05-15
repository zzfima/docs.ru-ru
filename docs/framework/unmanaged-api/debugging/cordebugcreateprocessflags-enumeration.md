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
ms.openlocfilehash: 9fdc37676bfae8ac90fde0a7a5b11037b8357e25
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="5cd75-102">Перечисление CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="5cd75-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="5cd75-103">Предоставляет дополнительные параметры отладки, которые могут использоваться в вызове [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="5cd75-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cd75-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5cd75-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5cd75-105">Members</span></span>  
  
|<span data-ttu-id="5cd75-106">Член</span><span class="sxs-lookup"><span data-stu-id="5cd75-106">Member</span></span>|<span data-ttu-id="5cd75-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd75-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="5cd75-108">Специальные параметры не заданы.</span><span class="sxs-lookup"><span data-stu-id="5cd75-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5cd75-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5cd75-109">Requirements</span></span>  
 <span data-ttu-id="5cd75-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd75-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cd75-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5cd75-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cd75-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cd75-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cd75-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd75-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd75-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5cd75-114">See Also</span></span>  
 [<span data-ttu-id="5cd75-115">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="5cd75-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
