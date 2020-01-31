---
title: Интерфейс ICorDebugAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: 9fb849c78636d5e29f58a70f59aa4cb3cd22df40
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784739"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="e46d6-102">Интерфейс ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="e46d6-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="e46d6-103">Предоставляет метод `Next`, который возвращает указанное число `ICorDebugAppDomainEnum` значений, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="e46d6-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="e46d6-104">Этот интерфейс является подклассом "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="e46d6-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e46d6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="e46d6-105">Methods</span></span>  
  
|<span data-ttu-id="e46d6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="e46d6-106">Method</span></span>|<span data-ttu-id="e46d6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e46d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e46d6-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="e46d6-108">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="e46d6-109">Возвращает указанное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="e46d6-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e46d6-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="e46d6-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e46d6-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="e46d6-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e46d6-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e46d6-112">Requirements</span></span>  
 <span data-ttu-id="e46d6-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e46d6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e46d6-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e46d6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e46d6-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e46d6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e46d6-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e46d6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e46d6-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e46d6-117">See also</span></span>

- [<span data-ttu-id="e46d6-118">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="e46d6-118">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="e46d6-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e46d6-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
