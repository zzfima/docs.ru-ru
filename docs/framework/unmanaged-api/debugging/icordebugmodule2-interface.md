---
title: "ICorDebugModule2 интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a3d62619fd83264bdc774cc1f09f4d98492d0a57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="08582-102">ICorDebugModule2 интерфейс1</span><span class="sxs-lookup"><span data-stu-id="08582-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="08582-103">Служит логическим расширением интерфейса ICorDebugModule-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="08582-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08582-104">Методы</span><span class="sxs-lookup"><span data-stu-id="08582-104">Methods</span></span>  
  
|<span data-ttu-id="08582-105">Метод</span><span class="sxs-lookup"><span data-stu-id="08582-105">Method</span></span>|<span data-ttu-id="08582-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="08582-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08582-107">Метод ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="08582-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="08582-108">Применяет изменения в метаданных и изменений в код на промежуточном языке (MSIL) к работающему процессу.</span><span class="sxs-lookup"><span data-stu-id="08582-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="08582-109">Метод GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="08582-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="08582-110">Получает флаги, управляющие компиляции just-in-time (JIT) для этого `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="08582-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="08582-111">Метод ResolveAssembly</span><span class="sxs-lookup"><span data-stu-id="08582-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="08582-112">Разрешает сборку ссылается указанный токен метаданных.</span><span class="sxs-lookup"><span data-stu-id="08582-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="08582-113">Метод SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="08582-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="08582-114">Задает флаги, управляющие JIT-компиляции для этого `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="08582-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="08582-115">Метод SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="08582-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="08582-116">Задает состояние "только мой код (") все методы для всех классов в этом `ICorDebugModule2` указанное значение, за исключением тех, в `pTokens` массив, который задает его значение с противоположным.</span><span class="sxs-lookup"><span data-stu-id="08582-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08582-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="08582-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08582-118">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="08582-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08582-119">Требования</span><span class="sxs-lookup"><span data-stu-id="08582-119">Requirements</span></span>  
 <span data-ttu-id="08582-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08582-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08582-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08582-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08582-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08582-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08582-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08582-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08582-124">См. также</span><span class="sxs-lookup"><span data-stu-id="08582-124">See Also</span></span>  
 [<span data-ttu-id="08582-125">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="08582-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
