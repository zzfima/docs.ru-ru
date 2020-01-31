---
title: Интерфейс ICorDebugThreadEnum
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum
helpviewer_keywords:
- ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: 796de687-7dd4-4b7b-a10b-8bf22dc7779f
topic_type:
- apiref
ms.openlocfilehash: 6de2cb7c1a1423c5bd38a6f2e5d01c39166ab119
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791320"
---
# <a name="icordebugthreadenum-interface"></a><span data-ttu-id="2ff24-102">Интерфейс ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="2ff24-102">ICorDebugThreadEnum Interface</span></span>
<span data-ttu-id="2ff24-103">Реализует методы ICorDebugEnum и перечисляет массивы ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="2ff24-103">Implements ICorDebugEnum methods and enumerates ICorDebugThread arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2ff24-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2ff24-104">Methods</span></span>  
  
|<span data-ttu-id="2ff24-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2ff24-105">Method</span></span>|<span data-ttu-id="2ff24-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2ff24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2ff24-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="2ff24-107">Next Method</span></span>](icordebugthreadenum-next-method.md)|<span data-ttu-id="2ff24-108">Возвращает указанное число экземпляров `ICorDebugThread` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="2ff24-108">Gets the specified number of `ICorDebugThread` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ff24-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="2ff24-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2ff24-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="2ff24-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ff24-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2ff24-111">Requirements</span></span>  
 <span data-ttu-id="2ff24-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ff24-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ff24-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2ff24-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2ff24-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2ff24-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2ff24-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ff24-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ff24-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="2ff24-116">See also</span></span>

- [<span data-ttu-id="2ff24-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2ff24-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
