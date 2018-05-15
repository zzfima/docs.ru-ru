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
ms.openlocfilehash: c5d3925741e9777e4fcd1752d8e24bf71ad1579f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="9501e-102">Метод ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="9501e-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="9501e-103">Возвращает размер в байтах, это [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="9501e-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9501e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9501e-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9501e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9501e-105">Parameters</span></span>  
 <span data-ttu-id="9501e-106">pSize</span><span class="sxs-lookup"><span data-stu-id="9501e-106">pSize</span></span>  
 <span data-ttu-id="9501e-107">[out] Указатель на размер в байтах этого объекта.</span><span class="sxs-lookup"><span data-stu-id="9501e-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9501e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9501e-108">Remarks</span></span>  
 <span data-ttu-id="9501e-109">Если это значение тип является ссылочным типом, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="9501e-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="9501e-110">`ICorDebugValue3::GetSize` Метод отличается от [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) метода в типе параметра выходных данных.</span><span class="sxs-lookup"><span data-stu-id="9501e-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="9501e-111">В [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), выходной параметр `ULONG32`, в `ICorDebugValue3::GetSize`, он является `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="9501e-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="9501e-112">Это позволяет [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) интерфейс для сообщения, размер которых превышает 2 ГБ массивов.</span><span class="sxs-lookup"><span data-stu-id="9501e-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9501e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9501e-113">Requirements</span></span>  
 <span data-ttu-id="9501e-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9501e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9501e-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9501e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9501e-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9501e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9501e-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9501e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9501e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9501e-118">See Also</span></span>  
 [<span data-ttu-id="9501e-119">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="9501e-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="9501e-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="9501e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
