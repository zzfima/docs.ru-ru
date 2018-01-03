---
title: "Перечисление CorDebugJITCompilerFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugJITCompilerFlags
helpviewer_keywords: CorDebugJITCompilerFlags enumeration [.NET Framework debugging]
ms.assetid: c0774f70-5bed-45e8-9922-fdad778c4c33
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfb78a160a7a6b9f50174fc8bb177cfd8d3f9383
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugjitcompilerflags-enumeration"></a><span data-ttu-id="95ef5-102">Перечисление CorDebugJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="95ef5-102">CorDebugJITCompilerFlags Enumeration</span></span>
<span data-ttu-id="95ef5-103">Содержит значения, которые влияют на поведение управляемого JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="95ef5-103">Contains values that influence the behavior of the managed just-in-time (JIT) compiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95ef5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95ef5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugJITCompilerFlags {  
  
    CORDEBUG_JIT_DEFAULT = 0x1,  
    CORDEBUG_JIT_DISABLE_OPTIMIZATION = 0x3,  
    CORDEBUG_JIT_ENABLE_ENC = 0x7  
  
} CorDebugJITCompilerFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="95ef5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="95ef5-105">Members</span></span>  
  
|<span data-ttu-id="95ef5-106">Член</span><span class="sxs-lookup"><span data-stu-id="95ef5-106">Member</span></span>|<span data-ttu-id="95ef5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="95ef5-107">Description</span></span>|  
|------------|-----------------|  
|`CORDEBUG_JIT_DEFAULT`|<span data-ttu-id="95ef5-108">Указывает, что компилятор должен отслеживать данные компиляции и позволяет выполнять оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="95ef5-108">Specifies that the compiler should track compilation data, and allows optimizations.</span></span>|  
|`CORDEBUG_JIT_DISABLE_OPTIMIZATION`|<span data-ttu-id="95ef5-109">Указывает, что компилятор должен отслеживать данные компиляции, но отключает оптимизацию.</span><span class="sxs-lookup"><span data-stu-id="95ef5-109">Specifies that the compiler should track compilation data, but disables optimizations.</span></span>|  
|`CORDEBUG_JIT_ENABLE_ENC`|<span data-ttu-id="95ef5-110">Указывает, что компилятор должен отслеживать данные компиляции, отключает синхронизацию и позволяет изменить и продолжить технологий.</span><span class="sxs-lookup"><span data-stu-id="95ef5-110">Specifies that the compiler should track compilation data, disables optimizations, and enables Edit and Continue technologies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95ef5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="95ef5-111">Requirements</span></span>  
 <span data-ttu-id="95ef5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95ef5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95ef5-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95ef5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95ef5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95ef5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95ef5-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95ef5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95ef5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="95ef5-116">See Also</span></span>  
 [<span data-ttu-id="95ef5-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="95ef5-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
