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
ms.openlocfilehash: 1ae40916807a86d1c9828080a6cb9e5c1d14c2ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671230"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="0ea12-102">Перечисление CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="0ea12-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="0ea12-103">Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="0ea12-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ea12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ea12-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="0ea12-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0ea12-105">Members</span></span>  
  
|<span data-ttu-id="0ea12-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="0ea12-106">Member name</span></span>|<span data-ttu-id="0ea12-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0ea12-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="0ea12-108">В [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] приложению, использование образов из локального кэша машинных образов отключен.</span><span class="sxs-lookup"><span data-stu-id="0ea12-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="0ea12-109">В настольном приложении этот параметр не влияет.</span><span class="sxs-lookup"><span data-stu-id="0ea12-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ea12-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ea12-110">Remarks</span></span>  
 <span data-ttu-id="0ea12-111">`CorDebugNGENPolicy` Перечисление, используемое [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0ea12-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="0ea12-112">Отключение использования образов из локального кэша машинных образов предоставляет для согласованности, гарантируя, что отладчик загружает отлаживаемых изображений, JIT-компиляции, вместо оптимизированные машинные образы.</span><span class="sxs-lookup"><span data-stu-id="0ea12-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ea12-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0ea12-113">Requirements</span></span>  
 <span data-ttu-id="0ea12-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ea12-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ea12-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ea12-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ea12-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ea12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ea12-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ea12-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea12-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0ea12-118">See also</span></span>
- [<span data-ttu-id="0ea12-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0ea12-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
