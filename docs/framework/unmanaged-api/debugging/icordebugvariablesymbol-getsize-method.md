---
title: 'Метод ICorDebugVariableSymbol:: resize'
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
ms.openlocfilehash: 61dad9522f9171166ca56a97e68b9a149d35e49a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121004"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="4dae5-102">Метод ICorDebugVariableSymbol:: resize</span><span class="sxs-lookup"><span data-stu-id="4dae5-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="4dae5-103">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="4dae5-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dae5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4dae5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4dae5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4dae5-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="4dae5-106">Указатель на 32-разрядное целое число без знака, содержащее размер переменной.</span><span class="sxs-lookup"><span data-stu-id="4dae5-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dae5-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="4dae5-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4dae5-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="4dae5-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dae5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4dae5-109">Requirements</span></span>  
 <span data-ttu-id="4dae5-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dae5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dae5-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4dae5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4dae5-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4dae5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4dae5-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dae5-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dae5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4dae5-114">See also</span></span>

- [<span data-ttu-id="4dae5-115">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="4dae5-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="4dae5-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4dae5-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
