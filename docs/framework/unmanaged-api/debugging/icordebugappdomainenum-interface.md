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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1fc949109455cf50767191a99a8a727116f77c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989512"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="3fbff-102">Интерфейс ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="3fbff-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="3fbff-103">Предоставляет `Next` метод, возвращающий заданное число `ICorDebugAppDomainEnum` значений, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="3fbff-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="3fbff-104">Этот интерфейс является подклассом «ICorDebugEnum».</span><span class="sxs-lookup"><span data-stu-id="3fbff-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fbff-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3fbff-105">Methods</span></span>  
  
|<span data-ttu-id="3fbff-106">Метод</span><span class="sxs-lookup"><span data-stu-id="3fbff-106">Method</span></span>|<span data-ttu-id="3fbff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3fbff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fbff-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="3fbff-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="3fbff-109">Возвращает указанное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="3fbff-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fbff-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fbff-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fbff-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="3fbff-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fbff-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3fbff-112">Requirements</span></span>  
 <span data-ttu-id="3fbff-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fbff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fbff-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fbff-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fbff-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fbff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fbff-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fbff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fbff-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3fbff-117">See also</span></span>

- [<span data-ttu-id="3fbff-118">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3fbff-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="3fbff-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3fbff-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
