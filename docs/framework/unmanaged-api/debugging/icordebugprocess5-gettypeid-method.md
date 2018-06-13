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
ms.openlocfilehash: b63c6ca8ead2a401f907ea6569e966c6470aca13
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421955"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="20d7b-102">Метод ICorDebugProcess5::GetTypeID</span><span class="sxs-lookup"><span data-stu-id="20d7b-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="20d7b-103">Преобразует объект адрес [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) идентификатор.</span><span class="sxs-lookup"><span data-stu-id="20d7b-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d7b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20d7b-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20d7b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="20d7b-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="20d7b-106">[in] Адрес объекта.</span><span class="sxs-lookup"><span data-stu-id="20d7b-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="20d7b-107">Указатель на [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) значение, которое определяет объект.</span><span class="sxs-lookup"><span data-stu-id="20d7b-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20d7b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="20d7b-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20d7b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="20d7b-109">Requirements</span></span>  
 <span data-ttu-id="20d7b-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20d7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d7b-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20d7b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20d7b-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20d7b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20d7b-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20d7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d7b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="20d7b-114">See Also</span></span>  
 [<span data-ttu-id="20d7b-115">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="20d7b-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="20d7b-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="20d7b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
