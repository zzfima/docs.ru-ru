---
title: Метод ICorDebugObjectValue::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: d15938e94d647fd5fded23c72bdc200d198d21a7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792702"
---
# <a name="icordebugobjectvaluegetclass-method"></a><span data-ttu-id="41c63-102">Метод ICorDebugObjectValue::GetClass</span><span class="sxs-lookup"><span data-stu-id="41c63-102">ICorDebugObjectValue::GetClass Method</span></span>
<span data-ttu-id="41c63-103">Возвращает класс этого значения объекта.</span><span class="sxs-lookup"><span data-stu-id="41c63-103">Gets the class of this object value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41c63-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41c63-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41c63-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="41c63-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="41c63-106">заполняет Указатель на адрес объекта "ICorDebugClass", который представляет класс значения объекта, представленного этим объектом "ICorDebugObjectValue".</span><span class="sxs-lookup"><span data-stu-id="41c63-106">[out] A pointer to the address of an "ICorDebugClass" object that represents the class of the object value represented by this "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41c63-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="41c63-107">Remarks</span></span>  
 <span data-ttu-id="41c63-108">Методы `GetClass` и [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) возвращают сведения о типе значения; они заменяются универсальными шаблонами [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="41c63-108">The `GetClass` and [ICorDebugValue::GetType](icordebugvalue-gettype-method.md) methods each return information about the type of a value; they are both superseded by the generics-aware [ICorDebugValue2::GetExactType](icordebugvalue2-getexacttype-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41c63-109">Требования</span><span class="sxs-lookup"><span data-stu-id="41c63-109">Requirements</span></span>  
 <span data-ttu-id="41c63-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41c63-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41c63-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41c63-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41c63-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41c63-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41c63-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41c63-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41c63-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="41c63-114">See also</span></span>
