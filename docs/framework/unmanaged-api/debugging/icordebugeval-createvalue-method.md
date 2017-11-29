---
title: "Метод ICorDebugEval::CreateValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.CreateValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7242e98a69083ca8d5a6d8d54e9b25279abb7bd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="79b8e-102">Метод ICorDebugEval::CreateValue</span><span class="sxs-lookup"><span data-stu-id="79b8e-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="79b8e-103">Создает значение заданного типа с начальным значением, равным нулю или null.</span><span class="sxs-lookup"><span data-stu-id="79b8e-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="79b8e-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="79b8e-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="79b8e-105">Используйте [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) вместо него.</span><span class="sxs-lookup"><span data-stu-id="79b8e-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79b8e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79b8e-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79b8e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="79b8e-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="79b8e-108">[in] Значение [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) перечисления, которое указывает тип значения.</span><span class="sxs-lookup"><span data-stu-id="79b8e-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="79b8e-109">[in] Указатель на [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) объекта, указывающее класс значения, если тип не является типом-примитивом.</span><span class="sxs-lookup"><span data-stu-id="79b8e-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="79b8e-110">[out] Указатель на адрес объекта «ICorDebugValue», который представляет значение.</span><span class="sxs-lookup"><span data-stu-id="79b8e-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79b8e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="79b8e-111">Remarks</span></span>  
 <span data-ttu-id="79b8e-112">`CreateValue`Создает `ICorDebugValue` объект заданного типа с единственной целью его использования при вычислении функции.</span><span class="sxs-lookup"><span data-stu-id="79b8e-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="79b8e-113">Этот объект значения можно использовать для передачи пользовательских констант в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="79b8e-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="79b8e-114">Если тип значения является типом-примитивом, его начальное значение равно нулю или иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="79b8e-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="79b8e-115">Используйте [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) требуется задать значение простого типа.</span><span class="sxs-lookup"><span data-stu-id="79b8e-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="79b8e-116">Если значение `elementType` — ELEMENT_TYPE_CLASS, вы получаете «ICorDebugReferenceValue» (возвращается в `ppValue`) представляет ссылку на объект null.</span><span class="sxs-lookup"><span data-stu-id="79b8e-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="79b8e-117">Этот объект можно использовать для передачи значения null вычисление функции, который имеет параметры ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="79b8e-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="79b8e-118">Не удается задать `ICorDebugValue` к любому другому объекту; он всегда возвращает значение null.</span><span class="sxs-lookup"><span data-stu-id="79b8e-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79b8e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="79b8e-119">Requirements</span></span>  
 <span data-ttu-id="79b8e-120">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b8e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79b8e-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79b8e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79b8e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79b8e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79b8e-123">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="79b8e-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79b8e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="79b8e-124">See Also</span></span>  
    
 [<span data-ttu-id="79b8e-125">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="79b8e-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 <span data-ttu-id="79b8e-126">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="79b8e-126">ICorDebugValue</span></span>
