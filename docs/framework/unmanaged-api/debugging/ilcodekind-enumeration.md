---
title: Перечисление ILCodeKind
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a02c26b72fc7039a5050ee369043f081c32cd7ec
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786022"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="c200a-102">Перечисление ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="c200a-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="c200a-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="c200a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c200a-104">Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="c200a-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c200a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c200a-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="c200a-106">Участники</span><span class="sxs-lookup"><span data-stu-id="c200a-106">Members</span></span>  
  
|<span data-ttu-id="c200a-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="c200a-107">Member name</span></span>|<span data-ttu-id="c200a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c200a-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="c200a-109">Отладчик не имеет доступа к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="c200a-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="c200a-110">Отладчик имеет доступ к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="c200a-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c200a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c200a-111">Remarks</span></span>  
 <span data-ttu-id="c200a-112">Является членом `ILCodeKind` перечисления может быть передан [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) и [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) методы, чтобы определить возможность доступа отладчика к переменным, добавленным в профилировщике Инструментарий ReJIT и [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) метод, чтобы определить, может ли отладчик доступ к инструментированному Промежуточному.</span><span class="sxs-lookup"><span data-stu-id="c200a-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c200a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c200a-113">Requirements</span></span>  
 <span data-ttu-id="c200a-114">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c200a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c200a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c200a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c200a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c200a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c200a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c200a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c200a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c200a-118">See Also</span></span>  
 [<span data-ttu-id="c200a-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c200a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="c200a-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="c200a-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="c200a-121">ReJIT: Практическое руководство</span><span class="sxs-lookup"><span data-stu-id="c200a-121">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
