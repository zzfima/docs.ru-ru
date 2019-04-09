---
title: Метод ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af4c7feb7076eeac6089a3255c7832c17a43469b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208843"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="685d3-102">Метод ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="685d3-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="685d3-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="685d3-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="685d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="685d3-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="685d3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="685d3-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="685d3-106">[out] Указатель на [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) значение, указывающее, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="685d3-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="685d3-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="685d3-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="685d3-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="685d3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="685d3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="685d3-109">Requirements</span></span>  
 <span data-ttu-id="685d3-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="685d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="685d3-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="685d3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="685d3-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="685d3-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="685d3-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="685d3-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="685d3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="685d3-114">See also</span></span>

- [<span data-ttu-id="685d3-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="685d3-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="685d3-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="685d3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
