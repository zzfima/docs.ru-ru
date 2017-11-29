---
title: "Метод ICorDebugObjectValue::GetFieldValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugObjectValue.GetFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33c3f368d9b78b899f54c989427ea1f660346487
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="f94b5-102">Метод ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="f94b5-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="f94b5-103">Возвращает значение указанного поля указанного класса для этого значения объекта.</span><span class="sxs-lookup"><span data-stu-id="f94b5-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f94b5-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f94b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f94b5-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="f94b5-106">[in] Указатель на объект «ICorDebugClass», который представляет класс, для которого необходимо получить значение поля.</span><span class="sxs-lookup"><span data-stu-id="f94b5-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="f94b5-107">[in] `mdFieldDef` Маркер, который ссылается на метаданные, описывающие поля.</span><span class="sxs-lookup"><span data-stu-id="f94b5-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f94b5-108">[out] Указатель на объект «ICorDebugValue», представляющее значение указанного поля.</span><span class="sxs-lookup"><span data-stu-id="f94b5-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f94b5-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f94b5-109">Remarks</span></span>  
 <span data-ttu-id="f94b5-110">Класс, заданный в `pClass` параметр, должен быть в иерархии класса значения объекта, а поле должно быть полем этого класса.</span><span class="sxs-lookup"><span data-stu-id="f94b5-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="f94b5-111">`GetFieldValue` Метод для универсальных объектов и универсальные классы пройдет успешно.</span><span class="sxs-lookup"><span data-stu-id="f94b5-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="f94b5-112">Например если MyDictionary\<V > наследует из словаря\<строка, V >, и значение объекта, которое имеет тип MyDictionary\<int32 > с передачей `ICorDebugClass` объект словаря\<K, V > будет успешно получен поле словаря\<string, int32 >.</span><span class="sxs-lookup"><span data-stu-id="f94b5-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f94b5-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f94b5-113">Requirements</span></span>  
 <span data-ttu-id="f94b5-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f94b5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f94b5-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f94b5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f94b5-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f94b5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f94b5-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f94b5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94b5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f94b5-118">See Also</span></span>  
    
 
