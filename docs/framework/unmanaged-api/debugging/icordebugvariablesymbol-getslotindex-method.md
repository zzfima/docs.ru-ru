---
title: Метод ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1657ed4d8326b573fe081b98c1fc414e231ac465
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420626"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="a81bd-102">Метод ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="a81bd-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="a81bd-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="a81bd-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a81bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a81bd-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a81bd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a81bd-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="a81bd-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="a81bd-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a81bd-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a81bd-107">Return Value</span></span>  
 <span data-ttu-id="a81bd-108">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="a81bd-108">`S_OK` if successful.</span></span> <span data-ttu-id="a81bd-109">`E_FAIL`, если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="a81bd-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a81bd-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="a81bd-110">Remarks</span></span>  
 <span data-ttu-id="a81bd-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="a81bd-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a81bd-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a81bd-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a81bd-113">Требования</span><span class="sxs-lookup"><span data-stu-id="a81bd-113">Requirements</span></span>  
 <span data-ttu-id="a81bd-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a81bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a81bd-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a81bd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a81bd-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a81bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a81bd-117">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a81bd-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a81bd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="a81bd-118">See Also</span></span>  
 [<span data-ttu-id="a81bd-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="a81bd-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="a81bd-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a81bd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
