---
title: Метод ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: 906ca2540e421953b3ce39300aa7b2376f789929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137103"
---
# <a name="icordebugvaluegetaddress-method"></a><span data-ttu-id="5c5a2-102">Метод ICorDebugValue::GetAddress</span><span class="sxs-lookup"><span data-stu-id="5c5a2-102">ICorDebugValue::GetAddress Method</span></span>
<span data-ttu-id="5c5a2-103">Возвращает адрес этого объекта "ICorDebugValue", который находится в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="5c5a2-103">Gets the address of this "ICorDebugValue" object, which is in the process of being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c5a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c5a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c5a2-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="5c5a2-106">заполняет Указатель на объект `CORDB_ADDRESS`, указывающий адрес этого объекта значения.</span><span class="sxs-lookup"><span data-stu-id="5c5a2-106">[out] Pointer to a `CORDB_ADDRESS` object that specifies the address of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c5a2-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="5c5a2-107">Remarks</span></span>  
 <span data-ttu-id="5c5a2-108">Если значение недоступно, возвращается 0 (нуль).</span><span class="sxs-lookup"><span data-stu-id="5c5a2-108">If the value is unavailable, 0 (zero) is returned.</span></span> <span data-ttu-id="5c5a2-109">Это может произойти, если значение по крайней мере частично находится в регистрах или хранится в обработчике сборщика мусора (`GCHandle`).</span><span class="sxs-lookup"><span data-stu-id="5c5a2-109">This could happen if the value is at least partly in registers or stored in a garbage collector handle (`GCHandle`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c5a2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5c5a2-110">Requirements</span></span>  
 <span data-ttu-id="5c5a2-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c5a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5a2-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c5a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c5a2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c5a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c5a2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5a2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="5c5a2-115">See also</span></span>
