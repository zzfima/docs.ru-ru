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
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178593"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="8b854-102">Метод ICorDebugProcess5::GetTypeFields</span><span class="sxs-lookup"><span data-stu-id="8b854-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="8b854-103">Предоставляет информацию о полях, которые принадлежат к типу.</span><span class="sxs-lookup"><span data-stu-id="8b854-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b854-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8b854-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b854-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8b854-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="8b854-106">(в) Идентификатор типа, информация о поле которого извлекается.</span><span class="sxs-lookup"><span data-stu-id="8b854-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="8b854-107">(в) Количество [COR_FIELD](cor-field-structure.md) объектов, информация о поле которых должна быть извлечена.</span><span class="sxs-lookup"><span data-stu-id="8b854-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="8b854-108">(ваут) Массив [COR_FIELD](cor-field-structure.md) объектов, предоставляющих информацию о полях, принадлежащих к типу.</span><span class="sxs-lookup"><span data-stu-id="8b854-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="8b854-109">(ваут) Указатель на количество [COR_FIELD](cor-field-structure.md) объектов, включенных в `fields`.</span><span class="sxs-lookup"><span data-stu-id="8b854-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b854-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8b854-110">Remarks</span></span>  
 <span data-ttu-id="8b854-111">Параметр, `celt` который определяет количество полей, поле информации метод `fields`использует для заполнения, должен `COR_TYPE_LAYOUT::numFields` соответствовать значению поля.</span><span class="sxs-lookup"><span data-stu-id="8b854-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b854-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8b854-112">Requirements</span></span>  
 <span data-ttu-id="8b854-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b854-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b854-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b854-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b854-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b854-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b854-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b854-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b854-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8b854-117">See also</span></span>

- [<span data-ttu-id="8b854-118">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="8b854-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="8b854-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8b854-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
