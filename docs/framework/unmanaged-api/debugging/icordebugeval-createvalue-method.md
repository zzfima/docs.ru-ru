---
title: Метод ICorDebugEval::CreateValue
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad40087ca61f1b07c0e0e36e785d89b84132962a
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759552"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="db2a5-102">Метод ICorDebugEval::CreateValue</span><span class="sxs-lookup"><span data-stu-id="db2a5-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="db2a5-103">Создает значение указанного типа, с начальным значением, равным нулю или null.</span><span class="sxs-lookup"><span data-stu-id="db2a5-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="db2a5-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="db2a5-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="db2a5-105">Используйте [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) вместо этого.</span><span class="sxs-lookup"><span data-stu-id="db2a5-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db2a5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db2a5-106">Syntax</span></span>  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db2a5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="db2a5-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="db2a5-108">[in] Значение [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) перечисление, указывающее тип значения.</span><span class="sxs-lookup"><span data-stu-id="db2a5-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="db2a5-109">[in] Указатель на [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) , указывающий класс значения, если тип не является типом-примитивом.</span><span class="sxs-lookup"><span data-stu-id="db2a5-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="db2a5-110">[out] Указатель на адрес объекта «ICorDebugValue», который представляет значение.</span><span class="sxs-lookup"><span data-stu-id="db2a5-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db2a5-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="db2a5-111">Remarks</span></span>  
 <span data-ttu-id="db2a5-112">`CreateValue` Создает `ICorDebugValue` объект заданного типа исключительно с целью его использования при вычислении функции.</span><span class="sxs-lookup"><span data-stu-id="db2a5-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="db2a5-113">Этот объект значения можно использовать для передачи пользовательских констант в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="db2a5-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="db2a5-114">Если тип значения является типом-примитивом, его начальное значение равно нулю или иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="db2a5-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="db2a5-115">Используйте [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) для задания значения типа-примитива.</span><span class="sxs-lookup"><span data-stu-id="db2a5-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="db2a5-116">Если значение `elementType` является ELEMENT_TYPE_CLASS, вы получаете «ICorDebugReferenceValue» (возвращается в `ppValue`) представляет ссылку на объект null.</span><span class="sxs-lookup"><span data-stu-id="db2a5-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="db2a5-117">Этот объект можно использовать для передачи значения null, имеющий параметры ссылки на объект вычисление функции.</span><span class="sxs-lookup"><span data-stu-id="db2a5-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="db2a5-118">Невозможно задать `ICorDebugValue` на любое другое; он всегда имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="db2a5-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db2a5-119">Требования</span><span class="sxs-lookup"><span data-stu-id="db2a5-119">Requirements</span></span>  
 <span data-ttu-id="db2a5-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db2a5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db2a5-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db2a5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db2a5-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db2a5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db2a5-123">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="db2a5-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2a5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="db2a5-124">See also</span></span>

- [<span data-ttu-id="db2a5-125">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="db2a5-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="db2a5-126">Интерфейс ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="db2a5-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
