---
title: Метод ICorDebugProcess5::GetTypeFields
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132674"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="42126-102">Метод ICorDebugProcess5::GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="42126-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="42126-103">Предоставляет сведения о полях, принадлежащих типу.</span><span class="sxs-lookup"><span data-stu-id="42126-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42126-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42126-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42126-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="42126-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="42126-106">окне Идентификатор типа, сведения о поле которого извлекаются.</span><span class="sxs-lookup"><span data-stu-id="42126-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="42126-107">окне Число объектов [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) , сведения о полях которых необходимо получить.</span><span class="sxs-lookup"><span data-stu-id="42126-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="42126-108">заполняет Массив объектов [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) , которые предоставляют сведения о полях, принадлежащих типу.</span><span class="sxs-lookup"><span data-stu-id="42126-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="42126-109">заполняет Указатель на число объектов [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) , включаемых в `fields`.</span><span class="sxs-lookup"><span data-stu-id="42126-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42126-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="42126-110">Remarks</span></span>  
 <span data-ttu-id="42126-111">Параметр `celt`, который указывает количество полей, сведения о полях которых использует метод для заполнения `fields`, должны соответствовать значению поля `COR_TYPE_LAYOUT::numFields`.</span><span class="sxs-lookup"><span data-stu-id="42126-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42126-112">Требования</span><span class="sxs-lookup"><span data-stu-id="42126-112">Requirements</span></span>  
 <span data-ttu-id="42126-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42126-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42126-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42126-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42126-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42126-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42126-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42126-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42126-117">См. также</span><span class="sxs-lookup"><span data-stu-id="42126-117">See also</span></span>

- [<span data-ttu-id="42126-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="42126-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="42126-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="42126-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
