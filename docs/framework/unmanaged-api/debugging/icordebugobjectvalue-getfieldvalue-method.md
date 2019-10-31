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
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095880"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a><span data-ttu-id="99d72-102">Метод ICorDebugObjectValue::GetFieldValue</span><span class="sxs-lookup"><span data-stu-id="99d72-102">ICorDebugObjectValue::GetFieldValue Method</span></span>
<span data-ttu-id="99d72-103">Возвращает значение указанного поля указанного класса для данного значения объекта.</span><span class="sxs-lookup"><span data-stu-id="99d72-103">Gets the value of the specified field of the specified class for this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99d72-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99d72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="99d72-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="99d72-106">окне Указатель на объект "ICorDebugClass", представляющий класс, для которого необходимо получить значение поля.</span><span class="sxs-lookup"><span data-stu-id="99d72-106">[in] A pointer to an "ICorDebugClass" object that represents the class for which to get the field value.</span></span>  
  
 `fieldDef`  
 <span data-ttu-id="99d72-107">окне Токен `mdFieldDef`, который ссылается на метаданные, описывающие поле.</span><span class="sxs-lookup"><span data-stu-id="99d72-107">[in] An `mdFieldDef` token that references the metadata describing the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="99d72-108">заполняет Указатель на объект "ICorDebugValue", представляющий значение указанного поля.</span><span class="sxs-lookup"><span data-stu-id="99d72-108">[out] A pointer to an "ICorDebugValue" object that represents the value of the specified field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99d72-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="99d72-109">Remarks</span></span>  
 <span data-ttu-id="99d72-110">Класс, указанный в параметре `pClass`, должен находиться в иерархии класса значения объекта, а поле должно быть полем этого класса.</span><span class="sxs-lookup"><span data-stu-id="99d72-110">The class, specified in the `pClass` parameter, must be in the hierarchy of the object value's class, and the field must be a field of that class.</span></span>  
  
 <span data-ttu-id="99d72-111">Метод `GetFieldValue` по-прежнему будет выполняться для универсальных объектов и универсальных классов.</span><span class="sxs-lookup"><span data-stu-id="99d72-111">The `GetFieldValue` method will still succeed for generic objects and generic classes.</span></span> <span data-ttu-id="99d72-112">Например, если Мидиктионари\<V > наследуется из словаря\<String, V >, а значение объекта имеет тип Мидиктионари\<Int32 >, передача `ICorDebugClass`ного объекта для Dictionary\<K, V > успешно получит поле\<словаря String, Int32 >.</span><span class="sxs-lookup"><span data-stu-id="99d72-112">For example, if MyDictionary\<V> inherits from Dictionary\<string,V>, and the object value is of type MyDictionary\<int32>, passing the `ICorDebugClass` object for Dictionary\<K,V> will successfully get a field of Dictionary\<string,int32>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99d72-113">Требования</span><span class="sxs-lookup"><span data-stu-id="99d72-113">Requirements</span></span>  
 <span data-ttu-id="99d72-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d72-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d72-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99d72-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99d72-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99d72-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99d72-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d72-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d72-118">См. также</span><span class="sxs-lookup"><span data-stu-id="99d72-118">See also</span></span>
