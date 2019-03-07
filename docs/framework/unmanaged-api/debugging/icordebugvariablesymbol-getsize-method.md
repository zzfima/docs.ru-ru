---
title: Метод ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 800c19574b24a4ab6135b53567515b23eae4dc8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494900"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="422f0-102">Метод ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="422f0-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="422f0-103">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="422f0-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="422f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="422f0-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="422f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="422f0-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="422f0-106">Указатель на 32-разрядное целое число без знака, содержащее размер переменной.</span><span class="sxs-lookup"><span data-stu-id="422f0-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="422f0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="422f0-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="422f0-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="422f0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="422f0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="422f0-109">Requirements</span></span>  
 <span data-ttu-id="422f0-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="422f0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="422f0-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="422f0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="422f0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="422f0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="422f0-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="422f0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="422f0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="422f0-114">See also</span></span>
- [<span data-ttu-id="422f0-115">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="422f0-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="422f0-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="422f0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
