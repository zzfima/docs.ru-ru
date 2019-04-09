---
title: Метод ICorDebugProcess5::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35fdcd4bc3c9dbf6408f501256ce0df0174f9374
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135659"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="3389e-102">Метод ICorDebugProcess5::GetObject</span><span class="sxs-lookup"><span data-stu-id="3389e-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="3389e-103">Преобразует адрес объекта в объект «ICorDebugObjectValue».</span><span class="sxs-lookup"><span data-stu-id="3389e-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3389e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3389e-104">Syntax</span></span>  
  
```  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3389e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3389e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="3389e-106">[in] Адрес объекта.</span><span class="sxs-lookup"><span data-stu-id="3389e-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="3389e-107">[out] Указатель на адрес объекта «ICorDebugObjectValue».</span><span class="sxs-lookup"><span data-stu-id="3389e-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3389e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3389e-108">Remarks</span></span>  
 <span data-ttu-id="3389e-109">Если `addr` не указывает на допустимый управляемого объекта, `GetObject` возвращает метод `E_FAIL`.</span><span class="sxs-lookup"><span data-stu-id="3389e-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3389e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3389e-110">Requirements</span></span>  
 <span data-ttu-id="3389e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3389e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3389e-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3389e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3389e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3389e-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3389e-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3389e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3389e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3389e-115">See also</span></span>

- [<span data-ttu-id="3389e-116">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="3389e-116">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="3389e-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3389e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
