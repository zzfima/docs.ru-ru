---
title: Метод ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbe6f6a2953c3f815606e881b86a693b7a0e6ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951901"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="8bd9d-102">Метод ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="8bd9d-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="8bd9d-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="8bd9d-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd9d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8bd9d-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bd9d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8bd9d-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="8bd9d-106">заполняет Указатель на значение [кордебужексцептионфлагс](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) , указывающее, может ли быть перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="8bd9d-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bd9d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8bd9d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8bd9d-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8bd9d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd9d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8bd9d-109">Requirements</span></span>  
 <span data-ttu-id="8bd9d-110">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bd9d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd9d-111">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8bd9d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bd9d-112">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="8bd9d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bd9d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd9d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd9d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8bd9d-114">See also</span></span>

- [<span data-ttu-id="8bd9d-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="8bd9d-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="8bd9d-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8bd9d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
