---
title: "Метод ICorDebugVariableSymbol::GetValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 90abece1-392e-4ade-94a1-30c75b0f7074
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ede5c92a13ad12667d282cf53a7498683dccfb92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetvalue-method"></a><span data-ttu-id="8c9bf-102">Метод ICorDebugVariableSymbol::GetValue</span><span class="sxs-lookup"><span data-stu-id="8c9bf-102">ICorDebugVariableSymbol::GetValue Method</span></span>
<span data-ttu-id="8c9bf-103">Возвращает значение переменной в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-103">Gets the value of a variable as a byte array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c9bf-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
   [in] ULONG32 offset,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [out] ULONG32 *pcbValue,  
   [out, size_is(cbValue), length_is(*pcbValue)] BYTE pValue[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c9bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8c9bf-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="8c9bf-106">[in] Начальное смещение в переменной, с которого следует читать значение.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-106">[in] The starting offset in the variable from which to read the value.</span></span> <span data-ttu-id="8c9bf-107">Этот параметр используется при чтении полей членов в объекте.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-107">This parameter is used when reading member fields in an object.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="8c9bf-108">[in] Размер аргумента `context` в байтах.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-108">[in] The size in bytes of the `context` argument.</span></span>  
  
 `context`  
 <span data-ttu-id="8c9bf-109">[in] Контекст потока, используемый для чтения значения.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-109">[in] The thread context used to read the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="8c9bf-110">[in] Размер буфера `pValue` в байтах.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-110">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pcbValue`  
 <span data-ttu-id="8c9bf-111">[out] Число байтов, фактически записанных в буфер `pValue`.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-111">[out] The number of bytes actually written to the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8c9bf-112">[out] Массив байтов, содержащий значение переменной.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-112">[out] A byte array that contains the value of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c9bf-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c9bf-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c9bf-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8c9bf-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c9bf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="8c9bf-115">Requirements</span></span>  
 <span data-ttu-id="8c9bf-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c9bf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c9bf-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c9bf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c9bf-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c9bf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c9bf-119">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c9bf-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c9bf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8c9bf-120">See Also</span></span>  
 [<span data-ttu-id="8c9bf-121">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="8c9bf-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="8c9bf-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c9bf-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
