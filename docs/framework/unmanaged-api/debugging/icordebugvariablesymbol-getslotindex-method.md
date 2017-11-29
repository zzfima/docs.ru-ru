---
title: "Метод ICorDebugVariableSymbol::GetSlotIndex"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d632bc792152afcfc94b51235dc0699fb3efc245
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="ef11b-102">Метод ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="ef11b-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="ef11b-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="ef11b-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef11b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef11b-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef11b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ef11b-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="ef11b-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="ef11b-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef11b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ef11b-107">Return Value</span></span>  
 <span data-ttu-id="ef11b-108">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="ef11b-108">`S_OK` if successful.</span></span> <span data-ttu-id="ef11b-109">`E_FAIL`, если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="ef11b-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef11b-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef11b-110">Remarks</span></span>  
 <span data-ttu-id="ef11b-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="ef11b-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef11b-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="ef11b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef11b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ef11b-113">Requirements</span></span>  
 <span data-ttu-id="ef11b-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef11b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef11b-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef11b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef11b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef11b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef11b-117">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef11b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef11b-118">См. также</span><span class="sxs-lookup"><span data-stu-id="ef11b-118">See Also</span></span>  
 [<span data-ttu-id="ef11b-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="ef11b-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="ef11b-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ef11b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
