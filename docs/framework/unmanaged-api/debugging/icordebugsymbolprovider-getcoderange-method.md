---
title: "Метод ICorDebugSymbolProvider::GetCodeRange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c46fb62e5f1867e2b527404bd3d003ba884ebfbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a><span data-ttu-id="6a546-102">Метод ICorDebugSymbolProvider::GetCodeRange</span><span class="sxs-lookup"><span data-stu-id="6a546-102">ICorDebugSymbolProvider::GetCodeRange Method</span></span>
<span data-ttu-id="6a546-103">Получает начальный адрес метода и размер с учетом относительного виртуального адреса (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="6a546-103">Gets the method start address and size given a relative virtual address (RVA) in a method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a546-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a546-104">Syntax</span></span>  
  
```  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,   
   [out] ULONG32* pCodeStartAddress,   
   [out] ULONG32* pCodeSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a546-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a546-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="6a546-106">[in] Относительный виртуальный адрес (RVA) в методе.</span><span class="sxs-lookup"><span data-stu-id="6a546-106">[in] The relative virtual address (RVA) in a method.</span></span>  
  
 `pCodeStartAddress`  
 <span data-ttu-id="6a546-107">[out] Указатель на начальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="6a546-107">[out] A pointer to the starting address of the method.</span></span>  
  
 `pCodeSize`  
 <span data-ttu-id="6a546-108">Указатель на размер кода метода (число байтов кода метода).</span><span class="sxs-lookup"><span data-stu-id="6a546-108">A pointer to the method code size (the number of bytes of the method's code).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a546-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a546-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a546-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6a546-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a546-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6a546-111">Requirements</span></span>  
 <span data-ttu-id="6a546-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a546-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a546-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a546-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a546-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a546-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a546-115">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a546-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a546-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6a546-116">See Also</span></span>  
 [<span data-ttu-id="6a546-117">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6a546-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="6a546-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6a546-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
