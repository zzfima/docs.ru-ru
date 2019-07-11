---
title: Метод ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbc320e13e0cb140f5ef7aa63b878b43ca0189b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750049"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="6d548-102">Метод ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="6d548-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="6d548-103">Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="6d548-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d548-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d548-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d548-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d548-105">Parameters</span></span>  
 <span data-ttu-id="6d548-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="6d548-106">pDebugEventKind</span></span>  
 <span data-ttu-id="6d548-107">Указатель на [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) член перечисления, указывающее тип события.</span><span class="sxs-lookup"><span data-stu-id="6d548-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d548-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d548-108">Remarks</span></span>  
 <span data-ttu-id="6d548-109">На основе значения `pDebugEventKind` можно вызвать `QueryInterface`, чтобы получить более точный интерфейс событий отладки, содержащий дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="6d548-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d548-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6d548-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d548-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6d548-111">Requirements</span></span>  
 <span data-ttu-id="6d548-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d548-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d548-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d548-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d548-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d548-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d548-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d548-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d548-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6d548-116">See also</span></span>

- [<span data-ttu-id="6d548-117">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="6d548-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="6d548-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6d548-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
