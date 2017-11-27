---
title: "Перечисление CorDebugNGenPolicy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugNGenPolicy
helpviewer_keywords: CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6042d5232995e68a4f59dfa68093446a03badfd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugngenpolicy-enumeration"></a><span data-ttu-id="ddf0b-102">Перечисление CorDebugNGenPolicy</span><span class="sxs-lookup"><span data-stu-id="ddf0b-102">CorDebugNGenPolicy Enumeration</span></span>
<span data-ttu-id="ddf0b-103">Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="ddf0b-103">Provides a value that determines whether a debugger loads native (NGen) images from the native image cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf0b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddf0b-104">Syntax</span></span>  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="ddf0b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ddf0b-105">Members</span></span>  
  
|<span data-ttu-id="ddf0b-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="ddf0b-106">Member name</span></span>|<span data-ttu-id="ddf0b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ddf0b-107">Description</span></span>|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|<span data-ttu-id="ddf0b-108">В [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] отключена приложения, использование образов из локального кэша машинных образов.</span><span class="sxs-lookup"><span data-stu-id="ddf0b-108">In a [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] app, the use of images from the local native image cache is disabled.</span></span> <span data-ttu-id="ddf0b-109">В приложении рабочего стола этот параметр не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="ddf0b-109">In a desktop app, this setting has no effect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddf0b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ddf0b-110">Remarks</span></span>  
 <span data-ttu-id="ddf0b-111">`CorDebugNGENPolicy` Перечисление используется методом [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="ddf0b-111">The `CorDebugNGENPolicy` enumeration is used by the [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) method.</span></span> <span data-ttu-id="ddf0b-112">Отключение использования образы из локального кэша машинных образов предоставляет для более согласованной отладки за счет того, что отладчик загружает отлаживаемых JIT-компиляции вместо изображения оптимизированные машинные образы.</span><span class="sxs-lookup"><span data-stu-id="ddf0b-112">Disabling the use of images from the local native image cache provides for a consistent debugging experience by ensuring that the debugger loads debuggable JIT-compiled images instead of optimized native images.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddf0b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ddf0b-113">Requirements</span></span>  
 <span data-ttu-id="ddf0b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf0b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf0b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddf0b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddf0b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddf0b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddf0b-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf0b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf0b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ddf0b-118">See Also</span></span>  
 [<span data-ttu-id="ddf0b-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="ddf0b-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
