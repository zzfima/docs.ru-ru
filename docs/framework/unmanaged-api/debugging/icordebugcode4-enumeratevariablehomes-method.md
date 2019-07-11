---
title: Метод ICorDebugCode4::EnumerateVariableHomes
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e6acdf6996f437c85b629b0af886287b1aef03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748556"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="5e031-102">Метод ICorDebugCode4::EnumerateVariableHomes</span><span class="sxs-lookup"><span data-stu-id="5e031-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="5e031-103">Получает перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="5e031-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e031-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e031-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e031-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e031-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5e031-106">Указатель на адрес [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) объект интерфейса, который является перечислителем для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="5e031-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e031-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e031-107">Remarks</span></span>  
 <span data-ttu-id="5e031-108">[ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) объект интерфейс является производным от «ICorDebugEnum» интерфейс, который позволяет перечислять стандартный перечислитель [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объектов.</span><span class="sxs-lookup"><span data-stu-id="5e031-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="5e031-109">Коллекции могут включать несколько [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) объектов для тот же индекс слота или аргумент, если они имеют разные домов в разные моменты в функции.</span><span class="sxs-lookup"><span data-stu-id="5e031-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e031-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5e031-110">Requirements</span></span>  
 <span data-ttu-id="5e031-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e031-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e031-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e031-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e031-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e031-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e031-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e031-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e031-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5e031-115">See also</span></span>

- [<span data-ttu-id="5e031-116">Интерфейс ICorDebugCode4</span><span class="sxs-lookup"><span data-stu-id="5e031-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="5e031-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5e031-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
