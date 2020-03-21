---
title: Метод ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: abc0e368f259df1a3542b0fc8e7fbfd7e06cf6eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178454"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="def0a-102">Метод ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="def0a-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="def0a-103">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="def0a-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="def0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="def0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="def0a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="def0a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="def0a-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="def0a-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="def0a-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="def0a-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="def0a-108">Указатель на массив символов, содержащий имя переменной.</span><span class="sxs-lookup"><span data-stu-id="def0a-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="def0a-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="def0a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="def0a-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="def0a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="def0a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="def0a-111">Requirements</span></span>  
 <span data-ttu-id="def0a-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="def0a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="def0a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="def0a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="def0a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="def0a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="def0a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="def0a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="def0a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="def0a-116">See also</span></span>

- [<span data-ttu-id="def0a-117">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="def0a-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="def0a-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="def0a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
