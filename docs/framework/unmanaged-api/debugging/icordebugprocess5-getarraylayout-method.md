---
title: Метод ICorDebugProcess5::GetArrayLayout
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 332de11790e78b712a429365bd89cc9e41539edc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105525"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="1b4ac-102">Метод ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="1b4ac-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="1b4ac-103">Предоставляет сведения о структуре типов массивов.</span><span class="sxs-lookup"><span data-stu-id="1b4ac-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b4ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b4ac-104">Syntax</span></span>  
  
```  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b4ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b4ac-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="1b4ac-106">[in] Объект [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) токен, который указывает заданный массив, в которых запрашиваются.</span><span class="sxs-lookup"><span data-stu-id="1b4ac-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="1b4ac-107">[out] Указатель на [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) структуру, содержащую сведения о макете массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="1b4ac-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b4ac-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b4ac-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b4ac-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1b4ac-109">Requirements</span></span>  
 <span data-ttu-id="1b4ac-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b4ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b4ac-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b4ac-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b4ac-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b4ac-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b4ac-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b4ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b4ac-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1b4ac-114">See also</span></span>

- [<span data-ttu-id="1b4ac-115">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="1b4ac-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="1b4ac-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1b4ac-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
