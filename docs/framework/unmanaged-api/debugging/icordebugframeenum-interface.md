---
title: Интерфейс ICorDebugFrameEnum
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum
helpviewer_keywords:
- ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: ee3f85d3-044e-46b8-945c-93ebfa5d9e91
topic_type:
- apiref
ms.openlocfilehash: 6cc1ef5f778902efaa53156fbefe334046c82114
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794537"
---
# <a name="icordebugframeenum-interface"></a><span data-ttu-id="0f4d0-102">Интерфейс ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="0f4d0-102">ICorDebugFrameEnum Interface</span></span>

<span data-ttu-id="0f4d0-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="0f4d0-103">Implements ICorDebugEnum methods, and enumerates ICorDebugFrame arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f4d0-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0f4d0-104">Methods</span></span>  
  
|<span data-ttu-id="0f4d0-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0f4d0-105">Method</span></span>|<span data-ttu-id="0f4d0-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0f4d0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f4d0-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="0f4d0-107">Next Method</span></span>](icordebugframeenum-next-method.md)|<span data-ttu-id="0f4d0-108">Возвращает указанное число экземпляров `ICorDebugFrame` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="0f4d0-108">Gets the specified number of `ICorDebugFrame` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f4d0-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="0f4d0-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f4d0-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="0f4d0-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f4d0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0f4d0-111">Requirements</span></span>  
 <span data-ttu-id="0f4d0-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f4d0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f4d0-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f4d0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f4d0-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f4d0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f4d0-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f4d0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4d0-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="0f4d0-116">See also</span></span>

- [<span data-ttu-id="0f4d0-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0f4d0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
