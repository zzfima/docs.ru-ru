---
title: Метод ICorDebugValue3::GetSize64
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c016c9dbe27f77b48c65fcd24ac9e13a9d07ed3f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485462"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="f8e54-102">Метод ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="f8e54-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="f8e54-103">Получает размер в байтах, это [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="f8e54-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e54-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f8e54-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8e54-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f8e54-105">Parameters</span></span>  
 <span data-ttu-id="f8e54-106">pSize</span><span class="sxs-lookup"><span data-stu-id="f8e54-106">pSize</span></span>  
 <span data-ttu-id="f8e54-107">[out] Указатель на размер в байтах этого объекта.</span><span class="sxs-lookup"><span data-stu-id="f8e54-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8e54-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="f8e54-108">Remarks</span></span>  
 <span data-ttu-id="f8e54-109">Если это значение тип является ссылочным типом, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="f8e54-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="f8e54-110">`ICorDebugValue3::GetSize` Метод отличается от [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) метода в типе параметра выходных данных.</span><span class="sxs-lookup"><span data-stu-id="f8e54-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="f8e54-111">В [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), выходной параметр имеет `ULONG32`, в списке `ICorDebugValue3::GetSize`, это `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="f8e54-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="f8e54-112">Это позволяет [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) интерфейс сообщить размер массивов, которые превышают 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="f8e54-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8e54-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f8e54-113">Requirements</span></span>  
 <span data-ttu-id="f8e54-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8e54-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8e54-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8e54-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8e54-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8e54-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8e54-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e54-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e54-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f8e54-118">See also</span></span>
- [<span data-ttu-id="f8e54-119">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="f8e54-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="f8e54-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f8e54-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
