---
title: 'Метод ICorDebugVariableSymbol:: GetSlotIndex'
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: a7a7ecf7d3e3d0d2125b03d3604c44138a2be0cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120970"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="e762a-102">Метод ICorDebugVariableSymbol:: GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="e762a-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="e762a-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="e762a-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e762a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e762a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e762a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e762a-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="e762a-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="e762a-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e762a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e762a-107">Return Value</span></span>  
 <span data-ttu-id="e762a-108">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="e762a-108">`S_OK` if successful.</span></span> <span data-ttu-id="e762a-109">`E_FAIL`, если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="e762a-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e762a-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="e762a-110">Remarks</span></span>  
 <span data-ttu-id="e762a-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="e762a-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e762a-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="e762a-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e762a-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e762a-113">Requirements</span></span>  
 <span data-ttu-id="e762a-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e762a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e762a-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e762a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e762a-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e762a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e762a-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e762a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e762a-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e762a-118">See also</span></span>

- [<span data-ttu-id="e762a-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="e762a-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="e762a-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e762a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
