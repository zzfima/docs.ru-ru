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
ms.openlocfilehash: 39f5c1813b08f4d72c610820b1434e29eb4aec8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121274"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="51166-102">Метод ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="51166-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="51166-103">Преобразует идентификатор типа в значение ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="51166-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51166-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51166-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51166-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51166-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="51166-106">окне Идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="51166-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="51166-107">заполняет Указатель на адрес объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="51166-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51166-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="51166-108">Remarks</span></span>  
 <span data-ttu-id="51166-109">В некоторых случаях методы, возвращающие идентификатор типа, могут возвращать значение NULL `COR_TYPEID`.</span><span class="sxs-lookup"><span data-stu-id="51166-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="51166-110">Если это значение передается в качестве аргумента `id`, метод `GetTypeForTypeID` завершится ошибкой и возвратит `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="51166-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51166-111">Требования</span><span class="sxs-lookup"><span data-stu-id="51166-111">Requirements</span></span>  
 <span data-ttu-id="51166-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51166-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51166-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51166-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51166-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51166-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51166-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51166-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51166-116">См. также</span><span class="sxs-lookup"><span data-stu-id="51166-116">See also</span></span>

- [<span data-ttu-id="51166-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="51166-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="51166-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="51166-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
