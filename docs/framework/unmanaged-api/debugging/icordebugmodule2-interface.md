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
ms.openlocfilehash: d3fb1bf3f61c78f4eb157b93363b1c06b25bee04
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119903"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="9a50e-102">Интерфейс ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="9a50e-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="9a50e-103">Служит логическим расширением ICorDebugModule-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9a50e-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a50e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9a50e-104">Methods</span></span>  
  
|<span data-ttu-id="9a50e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9a50e-105">Method</span></span>|<span data-ttu-id="9a50e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9a50e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a50e-107">Метод ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="9a50e-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="9a50e-108">Применяет изменения в метаданных и изменения в код на промежуточном языке (MSIL) к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="9a50e-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="9a50e-109">Метод GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="9a50e-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="9a50e-110">Получает флаги, определяющие компиляция just-in-time (JIT) для данного `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="9a50e-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="9a50e-111">Метод ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="9a50e-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="9a50e-112">Разрешает сборки, упоминаемой в заданным токеном метаданных.</span><span class="sxs-lookup"><span data-stu-id="9a50e-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="9a50e-113">Метод SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="9a50e-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="9a50e-114">Задает флаги, определяющие JIT-компиляция для данного `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="9a50e-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="9a50e-115">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="9a50e-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="9a50e-116">Задает состояние "только мой код (") все методы для всех классов в этом `ICorDebugModule2` указанное значение, за исключением тех, в `pTokens` массив, который задает противоположное значение.</span><span class="sxs-lookup"><span data-stu-id="9a50e-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a50e-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a50e-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a50e-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="9a50e-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a50e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="9a50e-119">Requirements</span></span>  
 <span data-ttu-id="9a50e-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a50e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a50e-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a50e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a50e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a50e-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9a50e-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9a50e-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9a50e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="9a50e-124">See also</span></span>

- [<span data-ttu-id="9a50e-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9a50e-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
