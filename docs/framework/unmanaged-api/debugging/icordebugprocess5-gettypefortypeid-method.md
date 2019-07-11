---
title: Метод ICorDebugProcess5::GetTypeForTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f37fab4d877ae804996f46290e3576cecc5a25ca
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767613"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="c584d-102">Метод ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="c584d-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="c584d-103">Преобразует идентификатор типа в значение ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="c584d-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c584d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c584d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c584d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c584d-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="c584d-106">[in] Идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="c584d-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c584d-107">[out] Указатель на адрес объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="c584d-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c584d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c584d-108">Remarks</span></span>  
 <span data-ttu-id="c584d-109">В некоторых случаях методы, возвращающие идентификатор типа могут вернуть значение null `COR_TYPEID` значение.</span><span class="sxs-lookup"><span data-stu-id="c584d-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="c584d-110">Если это значение передается как `id` аргумент, `GetTypeForTypeID` метод завершится ошибкой и вернет `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="c584d-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c584d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c584d-111">Requirements</span></span>  
 <span data-ttu-id="c584d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c584d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c584d-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c584d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c584d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c584d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c584d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c584d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c584d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c584d-116">See also</span></span>

- [<span data-ttu-id="c584d-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="c584d-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="c584d-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c584d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
