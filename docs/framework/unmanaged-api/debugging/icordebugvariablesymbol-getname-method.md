---
title: Метод ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170174"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="ecb9c-102">Метод ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="ecb9c-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="ecb9c-103">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="ecb9c-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb9c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecb9c-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecb9c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecb9c-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ecb9c-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="ecb9c-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ecb9c-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="ecb9c-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="ecb9c-108">Указатель на массив символов, содержащий имя переменной.</span><span class="sxs-lookup"><span data-stu-id="ecb9c-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecb9c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecb9c-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecb9c-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="ecb9c-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecb9c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ecb9c-111">Requirements</span></span>  
 <span data-ttu-id="ecb9c-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecb9c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecb9c-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecb9c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecb9c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecb9c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecb9c-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecb9c-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb9c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ecb9c-116">See also</span></span>

- [<span data-ttu-id="ecb9c-117">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="ecb9c-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="ecb9c-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ecb9c-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
