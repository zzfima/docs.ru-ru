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
ms.openlocfilehash: 6cc3ec1c802c28b74248380aa7f686e675a92f1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088842"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="cc151-102">Интерфейс ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="cc151-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="cc151-103">Предоставляет метод `Next`, который возвращает указанное число `ICorDebugAppDomainEnum` значений, начиная со следующего расположения в перечислении.</span><span class="sxs-lookup"><span data-stu-id="cc151-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="cc151-104">Этот интерфейс является подклассом "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="cc151-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cc151-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cc151-105">Methods</span></span>  
  
|<span data-ttu-id="cc151-106">Метод</span><span class="sxs-lookup"><span data-stu-id="cc151-106">Method</span></span>|<span data-ttu-id="cc151-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cc151-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cc151-108">Метод Next</span><span class="sxs-lookup"><span data-stu-id="cc151-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="cc151-109">Возвращает указанное число доменов приложений из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="cc151-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc151-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="cc151-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc151-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="cc151-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc151-112">Требования</span><span class="sxs-lookup"><span data-stu-id="cc151-112">Requirements</span></span>  
 <span data-ttu-id="cc151-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc151-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc151-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc151-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc151-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc151-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc151-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc151-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc151-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cc151-117">See also</span></span>

- [<span data-ttu-id="cc151-118">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="cc151-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="cc151-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="cc151-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
