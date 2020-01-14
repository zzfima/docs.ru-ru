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
ms.openlocfilehash: 553a92812f009ca1033f1bdcda0ea3722c5f01e3
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937839"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="14e9f-102">Перечисление ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="14e9f-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="14e9f-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="14e9f-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="14e9f-104">Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="14e9f-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e9f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14e9f-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="14e9f-106">Участники</span><span class="sxs-lookup"><span data-stu-id="14e9f-106">Members</span></span>  
  
|<span data-ttu-id="14e9f-107">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="14e9f-107">Member name</span></span>|<span data-ttu-id="14e9f-108">Описание</span><span class="sxs-lookup"><span data-stu-id="14e9f-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="14e9f-109">Отладчик не имеет доступа к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="14e9f-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="14e9f-110">Отладчик имеет доступ к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="14e9f-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e9f-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="14e9f-111">Remarks</span></span>  
 <span data-ttu-id="14e9f-112">Член перечисления `ILCodeKind` можно передать методам [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) и [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) , чтобы определить, может ли отладчик получить доступ к переменным, добавленным в инструментарий профилировщика ReJIT, а также к методу [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) , чтобы определить, может ли ОТЛАДЧИК получить доступ к инструментированному IL.</span><span class="sxs-lookup"><span data-stu-id="14e9f-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e9f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="14e9f-113">Requirements</span></span>  
 <span data-ttu-id="14e9f-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14e9f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e9f-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e9f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e9f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e9f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14e9f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e9f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e9f-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="14e9f-118">See also</span></span>

- [<span data-ttu-id="14e9f-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="14e9f-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="14e9f-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="14e9f-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="14e9f-121">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="14e9f-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
