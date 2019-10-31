---
title: 'Метод Икордебужексцептиондебужевент::'
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 6c330ce5b375daacdf257eda16fd5e34012f5d69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084757"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="d2e51-102">Метод Икордебужексцептиондебужевент::</span><span class="sxs-lookup"><span data-stu-id="d2e51-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="d2e51-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="d2e51-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2e51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2e51-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d2e51-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="d2e51-106">заполняет Указатель на значение [кордебужексцептионфлагс](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) , указывающее, может ли быть перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="d2e51-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2e51-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="d2e51-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2e51-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d2e51-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2e51-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d2e51-109">Requirements</span></span>  
 <span data-ttu-id="d2e51-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2e51-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2e51-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2e51-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2e51-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2e51-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2e51-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2e51-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2e51-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d2e51-114">See also</span></span>

- [<span data-ttu-id="d2e51-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d2e51-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="d2e51-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d2e51-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
