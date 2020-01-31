---
title: Интерфейс ICorDebugBlockingObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: be1e1cd0d38ad71de43478af5565bb1ac98a8c0d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777999"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="c436e-102">Интерфейс ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c436e-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="c436e-103">Предоставляет перечислитель для списка структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c436e-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="c436e-104">Этот интерфейс является подклассом интерфейса ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="c436e-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c436e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="c436e-105">Methods</span></span>  
  
|<span data-ttu-id="c436e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="c436e-106">Method</span></span>|<span data-ttu-id="c436e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c436e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c436e-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="c436e-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="c436e-109">Перечисляет по списку структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c436e-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c436e-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="c436e-110">Remarks</span></span>  
 <span data-ttu-id="c436e-111">Каждая структура `CorDebugBlockingObject` представляет объект, блокирующий поток.</span><span class="sxs-lookup"><span data-stu-id="c436e-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c436e-112">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="c436e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c436e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c436e-113">Requirements</span></span>  
 <span data-ttu-id="c436e-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c436e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c436e-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c436e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c436e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c436e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c436e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c436e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c436e-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c436e-118">See also</span></span>

- [<span data-ttu-id="c436e-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c436e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c436e-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="c436e-120">Debugging</span></span>](index.md)
