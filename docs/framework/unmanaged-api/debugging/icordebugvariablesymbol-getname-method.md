---
title: Метод ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23637055e493c008db36b23515001895450d6ab9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967906"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="9c07b-102">Метод ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="9c07b-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="9c07b-103">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="9c07b-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c07b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c07b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c07b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c07b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9c07b-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="9c07b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9c07b-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="9c07b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="9c07b-108">Указатель на массив символов, содержащий имя переменной.</span><span class="sxs-lookup"><span data-stu-id="9c07b-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c07b-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c07b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c07b-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="9c07b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c07b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9c07b-111">Requirements</span></span>  
 <span data-ttu-id="9c07b-112">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c07b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c07b-113">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9c07b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c07b-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="9c07b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c07b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c07b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c07b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9c07b-116">See also</span></span>

- [<span data-ttu-id="9c07b-117">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="9c07b-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="9c07b-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9c07b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
