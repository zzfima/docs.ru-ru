---
title: Метод ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73aa5a9ca6625ab58e451449fab4c98f8b83014e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422444"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="3d014-102">Метод ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="3d014-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="3d014-103">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="3d014-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d014-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d014-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d014-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d014-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3d014-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="3d014-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3d014-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="3d014-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="3d014-108">Указатель на массив символов, содержащий имя переменной.</span><span class="sxs-lookup"><span data-stu-id="3d014-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d014-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d014-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d014-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3d014-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d014-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3d014-111">Requirements</span></span>  
 <span data-ttu-id="3d014-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d014-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d014-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d014-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d014-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d014-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d014-115">**Версии платформы .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d014-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d014-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3d014-116">See Also</span></span>  
 [<span data-ttu-id="3d014-117">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="3d014-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="3d014-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3d014-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
