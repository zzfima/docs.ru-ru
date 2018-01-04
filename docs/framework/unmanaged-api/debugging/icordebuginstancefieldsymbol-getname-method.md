---
title: "Метод ICorDebugInstanceFieldSymbol::GetName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7071a640a5d3f379a03c45605cd6b3eb23c093ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="30ff5-102">Метод ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="30ff5-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="30ff5-103">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="30ff5-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ff5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30ff5-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30ff5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30ff5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="30ff5-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="30ff5-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="30ff5-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="30ff5-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="30ff5-108">[out] Массив символов, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="30ff5-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30ff5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="30ff5-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30ff5-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="30ff5-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ff5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="30ff5-111">Requirements</span></span>  
 <span data-ttu-id="30ff5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30ff5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30ff5-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30ff5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30ff5-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30ff5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30ff5-115">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30ff5-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ff5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="30ff5-116">See Also</span></span>  
 [<span data-ttu-id="30ff5-117">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="30ff5-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="30ff5-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="30ff5-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
