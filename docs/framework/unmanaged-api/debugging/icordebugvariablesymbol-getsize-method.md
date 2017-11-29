---
title: "Метод ICorDebugVariableSymbol::GetSize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: add0cd9d-9a29-49b1-ae07-d9d3786b4ccd
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ea4a77b08b12c3f067d51f9dfe2c961192c3354
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetsize-method"></a><span data-ttu-id="aa67b-102">Метод ICorDebugVariableSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="aa67b-102">ICorDebugVariableSymbol::GetSize Method</span></span>
<span data-ttu-id="aa67b-103">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="aa67b-103">Gets the size of a variable in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa67b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa67b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa67b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa67b-105">Parameters</span></span>  
 `pcbValue`  
 <span data-ttu-id="aa67b-106">Указатель на 32-разрядное целое число без знака, содержащее размер переменной.</span><span class="sxs-lookup"><span data-stu-id="aa67b-106">A pointer to a 32-bit unsigned integer containing the size of the variable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa67b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa67b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa67b-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="aa67b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa67b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="aa67b-109">Requirements</span></span>  
 <span data-ttu-id="aa67b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa67b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa67b-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa67b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa67b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa67b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa67b-113">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa67b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa67b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="aa67b-114">See Also</span></span>  
 [<span data-ttu-id="aa67b-115">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="aa67b-115">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="aa67b-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="aa67b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
