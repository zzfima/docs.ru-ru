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
ms.openlocfilehash: fea08331fffb85c91721d60764bae8bfe8b30e27
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928812"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="cfcbd-102">Перечисление ILCodeKind</span><span class="sxs-lookup"><span data-stu-id="cfcbd-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="cfcbd-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="cfcbd-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="cfcbd-104">Предоставляет значения, которые указывают, может ли отладчик получить доступ к локальным переменным или коду, добавленным в инструментарий ReJIT профилировщика.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfcbd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cfcbd-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="cfcbd-106">Участники</span><span class="sxs-lookup"><span data-stu-id="cfcbd-106">Members</span></span>  
  
|<span data-ttu-id="cfcbd-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="cfcbd-107">Member name</span></span>|<span data-ttu-id="cfcbd-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cfcbd-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="cfcbd-109">Отладчик не имеет доступа к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="cfcbd-110">Отладчик имеет доступ к информации из инструментария ReJIT.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfcbd-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cfcbd-111">Remarks</span></span>  
 <span data-ttu-id="cfcbd-112">Член `ILCodeKind` перечисления может быть передан методам [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) и [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) , чтобы определить, может ли отладчик получить доступ к переменным, добавленным в инструментарий профилировщика ReJIT, а также к элементу [ Метод GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) , чтобы определить, может ли отладчик получить доступ к инструментированному IL.</span><span class="sxs-lookup"><span data-stu-id="cfcbd-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfcbd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="cfcbd-113">Requirements</span></span>  
 <span data-ttu-id="cfcbd-114">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfcbd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfcbd-115">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="cfcbd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfcbd-116">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="cfcbd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfcbd-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfcbd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfcbd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cfcbd-118">See also</span></span>

- [<span data-ttu-id="cfcbd-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="cfcbd-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="cfcbd-120">Интерфейс ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="cfcbd-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="cfcbd-121">ReJIT Руководство</span><span class="sxs-lookup"><span data-stu-id="cfcbd-121">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
