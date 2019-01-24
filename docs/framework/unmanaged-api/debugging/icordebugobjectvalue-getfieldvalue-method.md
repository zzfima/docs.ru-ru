---
title: Метод ICorDebugObjectValue::GetFieldValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72a504d23b7b15ad3de72995a632843874cc7c5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631775"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="fd8b3-102">Метод ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="fd8b3-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="fd8b3-103">Получает значение указанного поля заданного класса для этого значения объекта.</span><span class="sxs-lookup"><span data-stu-id="fd8b3-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd8b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd8b3-104">Syntax</span></span>  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd8b3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd8b3-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="fd8b3-106">[in] Указатель на объект, представляющий класс, для которого необходимо получить значение поля «ICorDebugClass».</span><span class="sxs-lookup"><span data-stu-id="fd8b3-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="fd8b3-107">[in] `mdFieldDef` Маркер, который ссылается на метаданные, описывающие поле.</span><span class="sxs-lookup"><span data-stu-id="fd8b3-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="fd8b3-108">[out] Указатель на объект «ICorDebugValue», который представляет значение указанного поля.</span><span class="sxs-lookup"><span data-stu-id="fd8b3-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd8b3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd8b3-109">Remarks</span></span>  
 <span data-ttu-id="fd8b3-110">Класс, заданный в `pClass` параметр, должен быть в иерархии значение объекта класса, а поле должно быть полем этого класса.</span><span class="sxs-lookup"><span data-stu-id="fd8b3-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="fd8b3-111">`GetFieldValue` Метод все равно заканчивается успешно для универсальных объектов и классов.</span><span class="sxs-lookup"><span data-stu-id="fd8b3-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="fd8b3-112">Например если MyDictionary\<V > наследует из словаря\<string, V >, и значение объекта, которое имеет тип MyDictionary\<int32 >, передав `ICorDebugClass` объект словаря\<K, V > будет получить поля словаря\<string, int32 >.</span><span class="sxs-lookup"><span data-stu-id="fd8b3-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd8b3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fd8b3-113">Requirements</span></span>  
 <span data-ttu-id="fd8b3-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd8b3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd8b3-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd8b3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd8b3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd8b3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd8b3-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd8b3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd8b3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fd8b3-118">See also</span></span>


