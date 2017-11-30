---
title: "Метод ICorDebugVariableSymbol::GetName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aff18efb6781aee5b6a148fcd59863a2ce657023
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="f04ea-102">Метод ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="f04ea-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="f04ea-103">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f04ea-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f04ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f04ea-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f04ea-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f04ea-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f04ea-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="f04ea-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f04ea-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="f04ea-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f04ea-108">Указатель на массив символов, содержащий имя переменной.</span><span class="sxs-lookup"><span data-stu-id="f04ea-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f04ea-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f04ea-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f04ea-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f04ea-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f04ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f04ea-111">Requirements</span></span>  
 <span data-ttu-id="f04ea-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f04ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f04ea-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f04ea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f04ea-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f04ea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f04ea-115">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f04ea-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04ea-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f04ea-116">See Also</span></span>  
 [<span data-ttu-id="f04ea-117">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="f04ea-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="f04ea-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f04ea-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
