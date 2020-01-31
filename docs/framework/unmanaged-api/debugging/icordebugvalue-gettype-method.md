---
title: Метод ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 7def2bd2c0f3ab501fdb918a0e9a7ee154159b78
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791158"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="44f77-102">Метод ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="44f77-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="44f77-103">Возвращает тип примитива этого объекта "ICorDebugValue".</span><span class="sxs-lookup"><span data-stu-id="44f77-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44f77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44f77-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="44f77-106">заполняет Указатель на значение перечисления "Корелементтипе", которое указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="44f77-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44f77-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="44f77-107">Remarks</span></span>  
 <span data-ttu-id="44f77-108">Если объект является сложным типом времени выполнения, этот тип можно исследовать с помощью соответствующих подклассов интерфейса `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="44f77-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="44f77-109">Например, "ICorDebugObjectValue", который наследует от `ICorDebugValue`, представляет сложный тип.</span><span class="sxs-lookup"><span data-stu-id="44f77-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="44f77-110">Методы `GetType` и [ICorDebugObjectValue:: coclass](icordebugobjectvalue-getclass-method.md) возвращают сведения о типе значения.</span><span class="sxs-lookup"><span data-stu-id="44f77-110">The `GetType` and [ICorDebugObjectValue::GetClass](icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="44f77-111">Они заменяются методом [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) , поддерживающим универсальные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="44f77-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f77-112">Требования</span><span class="sxs-lookup"><span data-stu-id="44f77-112">Requirements</span></span>  
 <span data-ttu-id="44f77-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44f77-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f77-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44f77-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44f77-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44f77-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44f77-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f77-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f77-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="44f77-117">See also</span></span>
