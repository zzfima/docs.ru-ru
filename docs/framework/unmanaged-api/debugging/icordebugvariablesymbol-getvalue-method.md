---
title: 'Метод ICorDebugVariableSymbol:: GetValue'
ms.date: 03/30/2017
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
ms.openlocfilehash: 5ef7e67efb2bafd9b9f52203246fd7d1590e6107
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120967"
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="5a6c7-102">Метод ICorDebugVariableSymbol:: GetValue</span><span class="sxs-lookup"><span data-stu-id="5a6c7-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="5a6c7-103">Возвращает значение переменной в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a6c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a6c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5a6c7-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="5a6c7-106">[in] Начальное смещение в переменной, с которого следует читать значение.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="5a6c7-107">Этот параметр используется при чтении полей членов в объекте.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="5a6c7-108">[in] Размер аргумента `context` в байтах.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="5a6c7-109">[in] Контекст потока, используемый для чтения значения.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="5a6c7-110">[in] Размер буфера `pValue` в байтах.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="5a6c7-111">[out] Число байтов, фактически записанных в буфер `pValue`.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5a6c7-112">[out] Массив байтов, содержащий значение переменной.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a6c7-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="5a6c7-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a6c7-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5a6c7-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a6c7-115">Требования</span><span class="sxs-lookup"><span data-stu-id="5a6c7-115">Requirements</span></span>  
 <span data-ttu-id="5a6c7-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a6c7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a6c7-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a6c7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a6c7-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a6c7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a6c7-119">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a6c7-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6c7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5a6c7-120">See also</span></span>

- [<span data-ttu-id="5a6c7-121">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="5a6c7-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="5a6c7-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5a6c7-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
