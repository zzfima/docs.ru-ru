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
ms.openlocfilehash: bb25c9235e4fcded5c230d2d417b9d41bbdd9b19
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792339"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="bdafc-102">Метод ICorDebugProcess5::GetTypeForTypeID</span><span class="sxs-lookup"><span data-stu-id="bdafc-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="bdafc-103">Преобразует идентификатор типа в значение ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="bdafc-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdafc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdafc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdafc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdafc-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="bdafc-106">окне Идентификатор типа.</span><span class="sxs-lookup"><span data-stu-id="bdafc-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="bdafc-107">заполняет Указатель на адрес объекта ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="bdafc-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdafc-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="bdafc-108">Remarks</span></span>  
 <span data-ttu-id="bdafc-109">В некоторых случаях методы, возвращающие идентификатор типа, могут возвращать значение NULL `COR_TYPEID`.</span><span class="sxs-lookup"><span data-stu-id="bdafc-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="bdafc-110">Если это значение передается в качестве аргумента `id`, метод `GetTypeForTypeID` завершится ошибкой и возвратит `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="bdafc-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdafc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bdafc-111">Requirements</span></span>  
 <span data-ttu-id="bdafc-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdafc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdafc-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdafc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdafc-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdafc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdafc-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdafc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdafc-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="bdafc-116">See also</span></span>

- [<span data-ttu-id="bdafc-117">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="bdafc-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="bdafc-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bdafc-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
