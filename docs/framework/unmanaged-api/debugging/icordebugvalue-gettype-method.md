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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83265c4f6dffed76f1710378cf5293aac7020ef2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986899"
---
# <a name="icordebugvaluegettype-method"></a><span data-ttu-id="77f24-102">Метод ICorDebugValue::GetType</span><span class="sxs-lookup"><span data-stu-id="77f24-102">ICorDebugValue::GetType Method</span></span>
<span data-ttu-id="77f24-103">Возвращает примитивный тип объекта «ICorDebugValue».</span><span class="sxs-lookup"><span data-stu-id="77f24-103">Gets the primitive type of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f24-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77f24-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77f24-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="77f24-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="77f24-106">[out] Указатель на значение, указывающее тип значения перечисления «CorElementType».</span><span class="sxs-lookup"><span data-stu-id="77f24-106">[out] A pointer to a value of the "CorElementType" enumeration that indicates the value's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77f24-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="77f24-107">Remarks</span></span>  
 <span data-ttu-id="77f24-108">Если объект является сложного типа во время выполнения, этот тип можно проанализировать с помощью соответствующих подклассов `ICorDebugValue` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="77f24-108">If the object is a complex run-time type, that type may be examined through the appropriate subclasses of the `ICorDebugValue` interface.</span></span> <span data-ttu-id="77f24-109">Например, «ICorDebugObjectValue», который наследуется от `ICorDebugValue`, представляет сложный тип.</span><span class="sxs-lookup"><span data-stu-id="77f24-109">For example, "ICorDebugObjectValue", which inherits from `ICorDebugValue`, represents a complex type.</span></span>  
  
 <span data-ttu-id="77f24-110">`GetType` И [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) методы возвращают сведения о типе значения.</span><span class="sxs-lookup"><span data-stu-id="77f24-110">The `GetType` and [ICorDebugObjectValue::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) methods each return information about the type of a value.</span></span> <span data-ttu-id="77f24-111">Они оба заменяемые поддержкой универсальных типов [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="77f24-111">They are both superseded by the generics-aware [ICorDebugValue2::GetExactType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f24-112">Требования</span><span class="sxs-lookup"><span data-stu-id="77f24-112">Requirements</span></span>  
 <span data-ttu-id="77f24-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77f24-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f24-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77f24-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77f24-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77f24-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77f24-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f24-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f24-117">См. также</span><span class="sxs-lookup"><span data-stu-id="77f24-117">See also</span></span>
