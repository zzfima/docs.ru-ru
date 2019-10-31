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
ms.openlocfilehash: 4bb04ba090be9cab551bc39d8d9f1be974c747d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085133"
---
# <a name="icordebugevalcreatevalue-method"></a><span data-ttu-id="2c2ff-102">Метод ICorDebugEval::CreateValue</span><span class="sxs-lookup"><span data-stu-id="2c2ff-102">ICorDebugEval::CreateValue Method</span></span>
<span data-ttu-id="2c2ff-103">Создает значение указанного типа с начальным значением нуль или null.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-103">Creates a value of the specified type, with an initial value of zero or null.</span></span>  
  
 <span data-ttu-id="2c2ff-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2c2ff-105">Вместо этого используйте [ICorDebugEval2:: креатевалуефортипе](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2c2ff-105">Use [ICorDebugEval2::CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2ff-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c2ff-106">Syntax</span></span>  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c2ff-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c2ff-107">Parameters</span></span>  
 `elementType`  
 <span data-ttu-id="2c2ff-108">окне Значение перечисления [корелементтипе](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) , указывающее тип значения.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-108">[in] A value of the [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeration that specifies the type of the value.</span></span>  
  
 `pElementClass`  
 <span data-ttu-id="2c2ff-109">окне Указатель на объект [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) , указывающий класс значения, если тип не является типом-примитивом.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-109">[in] Pointer to an [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) object that specifies the class of the value, if the type is not a primitive type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="2c2ff-110">заполняет Указатель на адрес объекта "ICorDebugValue", представляющего значение.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-110">[out] Pointer to the address of an "ICorDebugValue" object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c2ff-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="2c2ff-111">Remarks</span></span>  
 <span data-ttu-id="2c2ff-112">`CreateValue` создает объект `ICorDebugValue` данного типа для единственной цели его использования в вычислении функции.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-112">`CreateValue` creates an `ICorDebugValue` object of the given type for the sole purpose of using it in a function evaluation.</span></span> <span data-ttu-id="2c2ff-113">Этот объект значения можно использовать для передачи пользовательских констант в качестве параметров.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-113">This value object can be used to pass user constants as parameters.</span></span>  
  
 <span data-ttu-id="2c2ff-114">Если тип значения является типом-примитивом, его начальное значение равно нулю или null.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-114">If the type of the value is a primitive type, its initial value is zero or null.</span></span> <span data-ttu-id="2c2ff-115">Используйте [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) , чтобы задать значение типа-примитива.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-115">Use [ICorDebugGenericValue::SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) to set the value of a primitive type.</span></span>  
  
 <span data-ttu-id="2c2ff-116">Если значение `elementType` ELEMENT_TYPE_CLASS, вы получаете "ICorDebugReferenceValue" (возвращается в `ppValue`), представляющий ссылку на пустой объект.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-116">If the value of `elementType` is ELEMENT_TYPE_CLASS, you get an "ICorDebugReferenceValue" (returned in `ppValue`) representing the null object reference.</span></span> <span data-ttu-id="2c2ff-117">Этот объект можно использовать для передачи значения NULL в вычисление функции, имеющей параметры ссылки на объект.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-117">You can use this object to pass null to a function evaluation that has object reference parameters.</span></span> <span data-ttu-id="2c2ff-118">Вы не можете задать для `ICorDebugValue` любое значение; Он всегда остается пустым.</span><span class="sxs-lookup"><span data-stu-id="2c2ff-118">You cannot set the `ICorDebugValue` to anything; it always remains null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c2ff-119">Требования</span><span class="sxs-lookup"><span data-stu-id="2c2ff-119">Requirements</span></span>  
 <span data-ttu-id="2c2ff-120">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2ff-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2ff-121">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c2ff-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c2ff-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c2ff-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c2ff-123">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="2c2ff-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2ff-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2c2ff-124">See also</span></span>

- [<span data-ttu-id="2c2ff-125">Метод CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="2c2ff-125">CreateValueForType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [<span data-ttu-id="2c2ff-126">Интерфейс ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="2c2ff-126">ICorDebugEval Interface</span></span>](icordebugeval-interface.md)
