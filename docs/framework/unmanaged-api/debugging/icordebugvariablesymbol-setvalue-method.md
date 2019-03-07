---
title: Метод ICorDebugVariableSymbol::SetValue
ms.date: 03/30/2017
ms.assetid: 4609418d-71fa-44bc-9618-4d529d25cabb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b83efca5a8b175d5dc83c03de473262ca033354c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491312"
---
# <a name="icordebugvariablesymbolsetvalue-method"></a><span data-ttu-id="05a25-102">Метод ICorDebugVariableSymbol::SetValue</span><span class="sxs-lookup"><span data-stu-id="05a25-102">ICorDebugVariableSymbol::SetValue Method</span></span>
<span data-ttu-id="05a25-103">Присваивает переменной значение массива байтов.</span><span class="sxs-lookup"><span data-stu-id="05a25-103">Assigns the value of a byte array to a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05a25-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05a25-104">Syntax</span></span>  
  
```  
HRESULT SetValue(  
   [in] ULONG32 offset,  
   [in] DWORD threadID,  
   [in] ULONG32 cbContext,  
   [in, size_is(cbContext)] BYTE context[],  
   [in] ULONG32 cbValue,  
   [in, size_is(cbValue)] BYTE pValue[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05a25-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="05a25-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="05a25-106">[in] Начальное смещение в переменной, с которого следует задавать значение.</span><span class="sxs-lookup"><span data-stu-id="05a25-106">[in] The starting offset in the variable at which to set the value.</span></span> <span data-ttu-id="05a25-107">Этот параметр используется при записи в поля членов в объекте.</span><span class="sxs-lookup"><span data-stu-id="05a25-107">This parameter is used when writing to member fields in an object.</span></span>  
  
 `threadID`  
 <span data-ttu-id="05a25-108">[in] Идентификатор потока, чей контекст должен быть обновлен в соответствии с новым значением.</span><span class="sxs-lookup"><span data-stu-id="05a25-108">[in] The thread identifier of the thread whose context must be updated to reflect the new value.</span></span>  
  
 `cbContext`  
 <span data-ttu-id="05a25-109">[in] Размер контекста потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="05a25-109">[in] The size in bytes of the thread context.</span></span>  
  
 `context`  
 <span data-ttu-id="05a25-110">[in] Контекст потока, используемый для записи значения.</span><span class="sxs-lookup"><span data-stu-id="05a25-110">[in] The thread context used to write the value.</span></span>  
  
 `cbValue`  
 <span data-ttu-id="05a25-111">[in] Размер буфера `pValue` в байтах.</span><span class="sxs-lookup"><span data-stu-id="05a25-111">[in] The size in bytes of the `pValue` buffer.</span></span>  
  
 `pValue`  
 <span data-ttu-id="05a25-112">[in] Буфер, содержащий значение, которое требуется задать.</span><span class="sxs-lookup"><span data-stu-id="05a25-112">[in] The buffer that contains the value to set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05a25-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="05a25-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05a25-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="05a25-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05a25-115">Требования</span><span class="sxs-lookup"><span data-stu-id="05a25-115">Requirements</span></span>  
 <span data-ttu-id="05a25-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05a25-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05a25-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05a25-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05a25-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05a25-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05a25-119">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05a25-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a25-120">См. также</span><span class="sxs-lookup"><span data-stu-id="05a25-120">See also</span></span>
- [<span data-ttu-id="05a25-121">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="05a25-121">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="05a25-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="05a25-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
