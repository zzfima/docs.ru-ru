---
title: Интерфейс ICorDebugModule2
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 192f2476aff91d3a8302d070852ab2a3722d137c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970133"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="73bf6-102">Интерфейс ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="73bf6-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="73bf6-103">Служит логическим расширением ICorDebugModule-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="73bf6-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73bf6-104">Методы</span><span class="sxs-lookup"><span data-stu-id="73bf6-104">Methods</span></span>  
  
|<span data-ttu-id="73bf6-105">Метод</span><span class="sxs-lookup"><span data-stu-id="73bf6-105">Method</span></span>|<span data-ttu-id="73bf6-106">Описание</span><span class="sxs-lookup"><span data-stu-id="73bf6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73bf6-107">Метод ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="73bf6-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="73bf6-108">Применяет изменения в метаданных и изменения в код на промежуточном языке (MSIL) к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="73bf6-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="73bf6-109">Метод GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="73bf6-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="73bf6-110">Получает флаги, определяющие компиляция just-in-time (JIT) для данного `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="73bf6-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="73bf6-111">Метод ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="73bf6-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="73bf6-112">Разрешает сборки, упоминаемой в заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="73bf6-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="73bf6-113">Метод SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="73bf6-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="73bf6-114">Задает флаги, определяющие JIT-компиляция для данного `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="73bf6-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="73bf6-115">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="73bf6-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="73bf6-116">Задает состояние "только мой код (") все методы для всех классов в этом `ICorDebugModule2` указанное значение, за исключением тех, в `pTokens` массив, который задает противоположное значение.</span><span class="sxs-lookup"><span data-stu-id="73bf6-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73bf6-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="73bf6-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73bf6-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="73bf6-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73bf6-119">Требования</span><span class="sxs-lookup"><span data-stu-id="73bf6-119">Requirements</span></span>  
 <span data-ttu-id="73bf6-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73bf6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73bf6-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73bf6-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73bf6-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73bf6-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73bf6-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73bf6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73bf6-124">См. также</span><span class="sxs-lookup"><span data-stu-id="73bf6-124">See also</span></span>
- [<span data-ttu-id="73bf6-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="73bf6-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
