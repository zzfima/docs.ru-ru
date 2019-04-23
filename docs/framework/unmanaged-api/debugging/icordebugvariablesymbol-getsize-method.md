---
title: Метод ICorDebugVariableSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 027b3f773ff0ed0ca7bf9d193f97a3b060ea8494
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211846"
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="d9714-102">Метод ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="d9714-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="d9714-103">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="d9714-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9714-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9714-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9714-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9714-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="d9714-106">Указатель на 32-разрядное целое число без знака, содержащее размер переменной.</span><span class="sxs-lookup"><span data-stu-id="d9714-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9714-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9714-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9714-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d9714-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9714-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d9714-109">Requirements</span></span>  
 <span data-ttu-id="d9714-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9714-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9714-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9714-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9714-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9714-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9714-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9714-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9714-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d9714-114">See also</span></span>

- [<span data-ttu-id="d9714-115">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="d9714-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="d9714-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d9714-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
