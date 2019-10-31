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
ms.openlocfilehash: 5a415c8f3124c08984f8101e1f4dbcae6bf96fbf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129612"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="911da-102">Метод ICorDebugProcess5::GetArrayLayout</span><span class="sxs-lookup"><span data-stu-id="911da-102">ICorDebugProcess5::GetArrayLayout Method</span></span>
<span data-ttu-id="911da-103">Предоставляет сведения о структуре типов массивов.</span><span class="sxs-lookup"><span data-stu-id="911da-103">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="911da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="911da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="911da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="911da-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="911da-106">окне Токен [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) , указывающий массив, макет которого требуется.</span><span class="sxs-lookup"><span data-stu-id="911da-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="911da-107">заполняет Указатель на структуру [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) , содержащую сведения о макете массива в памяти.</span><span class="sxs-lookup"><span data-stu-id="911da-107">[out] A pointer to a [COR_ARRAY_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="911da-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="911da-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="911da-109">Требования</span><span class="sxs-lookup"><span data-stu-id="911da-109">Requirements</span></span>  
 <span data-ttu-id="911da-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="911da-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="911da-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="911da-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="911da-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="911da-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="911da-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="911da-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="911da-114">См. также</span><span class="sxs-lookup"><span data-stu-id="911da-114">See also</span></span>

- [<span data-ttu-id="911da-115">Интерфейс ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="911da-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="911da-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="911da-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
