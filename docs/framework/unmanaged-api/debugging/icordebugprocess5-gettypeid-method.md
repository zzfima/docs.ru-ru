---
title: Метод ICorDebugProcess5::GetTypeID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07c23a32037e83a878bb3136c48176f19249b207
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948698"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="2f8a6-102">Метод ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="2f8a6-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="2f8a6-103">Преобразует объект адрес [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) идентификатор.</span><span class="sxs-lookup"><span data-stu-id="2f8a6-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f8a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f8a6-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f8a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f8a6-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="2f8a6-106">[in] Адрес объекта.</span><span class="sxs-lookup"><span data-stu-id="2f8a6-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="2f8a6-107">Указатель на [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) значение, которое определяет объект.</span><span class="sxs-lookup"><span data-stu-id="2f8a6-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f8a6-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f8a6-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f8a6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="2f8a6-109">Requirements</span></span>  
 <span data-ttu-id="2f8a6-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f8a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f8a6-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f8a6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f8a6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f8a6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f8a6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f8a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8a6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="2f8a6-114">See also</span></span>

- [<span data-ttu-id="2f8a6-115">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="2f8a6-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="2f8a6-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2f8a6-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
