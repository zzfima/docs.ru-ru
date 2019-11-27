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
ms.openlocfilehash: 2f8337f96239948189ffd58923d87fd05c79b0c3
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204860"
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="efacd-102">Перечисление CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="efacd-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="efacd-103">Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="efacd-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efacd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efacd-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="efacd-105">Члены</span><span class="sxs-lookup"><span data-stu-id="efacd-105">Members</span></span>  
  
|<span data-ttu-id="efacd-106">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="efacd-106">Member name</span></span>|<span data-ttu-id="efacd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="efacd-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="efacd-108">В приложении для Магазина Windows 8. x использование образов из локального кэша образов в машинном кодах отключено.</span><span class="sxs-lookup"><span data-stu-id="efacd-108">In a Windows 8.x Store app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="efacd-109">В классическом приложении этот параметр не действует.</span><span class="sxs-lookup"><span data-stu-id="efacd-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efacd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="efacd-110">Remarks</span></span>  
 <span data-ttu-id="efacd-111">Перечисление `CorDebugNGENPolicy` используется методом [метод ICorDebugProcess5:: EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="efacd-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="efacd-112">Отключение использования образов из локального кэша образов в машинном код обеспечивает единообразную отладку, гарантируя, что отладчик загружает отладочные скомпилированные КОМПИЛЯТОРом изображения вместо оптимизированных образов в машинном код.</span><span class="sxs-lookup"><span data-stu-id="efacd-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efacd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="efacd-113">Requirements</span></span>  
 <span data-ttu-id="efacd-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efacd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efacd-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efacd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efacd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efacd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efacd-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efacd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efacd-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="efacd-118">See also</span></span>

- [<span data-ttu-id="efacd-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="efacd-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
