---
title: Перечисление CorDebugNGenPolicy
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca922d8b582c0608073d4fd0ba986167ae470e34
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109672"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="9b6f2-102">Перечисление CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="9b6f2-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="9b6f2-103">Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="9b6f2-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b6f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b6f2-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="9b6f2-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9b6f2-105">Members</span></span>  
  
|<span data-ttu-id="9b6f2-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="9b6f2-106">Member name</span></span>|<span data-ttu-id="9b6f2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9b6f2-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="9b6f2-108">В [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] приложению, использование образов из локального кэша машинных образов отключен.</span><span class="sxs-lookup"><span data-stu-id="9b6f2-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="9b6f2-109">В настольном приложении этот параметр не влияет.</span><span class="sxs-lookup"><span data-stu-id="9b6f2-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b6f2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b6f2-110">Remarks</span></span>  
 <span data-ttu-id="9b6f2-111">`CorDebugNGENPolicy` Перечисление, используемое [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9b6f2-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="9b6f2-112">Отключение использования образов из локального кэша машинных образов предоставляет для согласованности, гарантируя, что отладчик загружает отлаживаемых изображений, JIT-компиляции, вместо оптимизированные машинные образы.</span><span class="sxs-lookup"><span data-stu-id="9b6f2-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b6f2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9b6f2-113">Requirements</span></span>  
 <span data-ttu-id="9b6f2-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b6f2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b6f2-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b6f2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b6f2-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b6f2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b6f2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b6f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b6f2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9b6f2-118">See also</span></span>

- [<span data-ttu-id="9b6f2-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="9b6f2-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
