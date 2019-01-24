---
title: Метод ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a41ec4a556ca26404b5f76ddb35d9f73d7307a7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659060"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="55c2b-102">Метод ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="55c2b-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="55c2b-103">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="55c2b-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55c2b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55c2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55c2b-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="55c2b-106">Указатель на 32-разрядное целое число без знака, содержащее размер переменной.</span><span class="sxs-lookup"><span data-stu-id="55c2b-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c2b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="55c2b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55c2b-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="55c2b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55c2b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="55c2b-109">Requirements</span></span>  
 <span data-ttu-id="55c2b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c2b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c2b-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55c2b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55c2b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55c2b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55c2b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c2b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c2b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="55c2b-114">See also</span></span>
- [<span data-ttu-id="55c2b-115">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="55c2b-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="55c2b-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="55c2b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
