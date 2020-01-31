---
title: Метод ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 3510daffb55bdb22aa5f835bf27157e7c8428509
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790895"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="a6b21-102">Метод ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="a6b21-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="a6b21-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="a6b21-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6b21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6b21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6b21-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="a6b21-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="a6b21-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6b21-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a6b21-107">Return Value</span></span>  
 <span data-ttu-id="a6b21-108">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="a6b21-108">`S_OK` if successful.</span></span> <span data-ttu-id="a6b21-109">`E_FAIL`, если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="a6b21-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6b21-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="a6b21-110">Remarks</span></span>  
 <span data-ttu-id="a6b21-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="a6b21-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6b21-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a6b21-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6b21-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a6b21-113">Requirements</span></span>  
 <span data-ttu-id="a6b21-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6b21-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b21-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6b21-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6b21-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6b21-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6b21-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b21-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b21-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="a6b21-118">See also</span></span>

- [<span data-ttu-id="a6b21-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="a6b21-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="a6b21-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a6b21-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
