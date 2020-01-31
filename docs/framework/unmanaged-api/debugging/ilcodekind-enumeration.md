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
ms.openlocfilehash: 20e2e3f177b12221832786f4fab86635098d1989
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790491"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="238f1-102">Перечисление ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="238f1-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="238f1-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="238f1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="238f1-104">Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="238f1-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="238f1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="238f1-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="238f1-106">Участники</span><span class="sxs-lookup"><span data-stu-id="238f1-106">Members</span></span>  
  
|<span data-ttu-id="238f1-107">Имя элемента</span><span class="sxs-lookup"><span data-stu-id="238f1-107">Member name</span></span>|<span data-ttu-id="238f1-108">Описание</span><span class="sxs-lookup"><span data-stu-id="238f1-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="238f1-109">Отладчик не имеет доступа к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="238f1-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="238f1-110">Отладчик имеет доступ к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="238f1-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="238f1-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="238f1-111">Remarks</span></span>  
 <span data-ttu-id="238f1-112">Член перечисления `ILCodeKind` можно передать методам [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) и [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) , чтобы определить, может ли отладчик получить доступ к переменным, добавленным в инструментарий профилировщика ReJIT, а также к методу [GetCodeEx](icordebugilframe4-getcodeex-method.md) , чтобы определить, может ли ОТЛАДЧИК получить доступ к инструментированному IL.</span><span class="sxs-lookup"><span data-stu-id="238f1-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="238f1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="238f1-113">Requirements</span></span>  
 <span data-ttu-id="238f1-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="238f1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="238f1-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="238f1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="238f1-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="238f1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="238f1-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="238f1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="238f1-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="238f1-118">See also</span></span>

- [<span data-ttu-id="238f1-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="238f1-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="238f1-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="238f1-120">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="238f1-121">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="238f1-121">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
