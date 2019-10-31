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
ms.openlocfilehash: 72a1b6fdc40f3169500d8cf3b3028315106ecc69
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140228"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="e1748-102">Метод ICorDebugValue3::GetSize64</span><span class="sxs-lookup"><span data-stu-id="e1748-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="e1748-103">Возвращает размер данного объекта [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) в байтах.</span><span class="sxs-lookup"><span data-stu-id="e1748-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1748-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1748-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1748-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e1748-105">Parameters</span></span>  
 <span data-ttu-id="e1748-106">псизе</span><span class="sxs-lookup"><span data-stu-id="e1748-106">pSize</span></span>  
 <span data-ttu-id="e1748-107">заполняет Указатель на размер данного объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="e1748-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1748-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e1748-108">Remarks</span></span>  
 <span data-ttu-id="e1748-109">Если этот тип значения является ссылочным, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="e1748-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="e1748-110">Метод `ICorDebugValue3::GetSize` отличается от метода [ICorDebugValue:: resize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) в типе выходного параметра.</span><span class="sxs-lookup"><span data-stu-id="e1748-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="e1748-111">В [ICorDebugValue::-size](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)выходной параметр является `ULONG32`; в `ICorDebugValue3::GetSize`это `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="e1748-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="e1748-112">Это позволяет интерфейсу [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) сообщать размер массивов, ПРЕВЫШАЮЩИХ 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="e1748-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1748-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e1748-113">Requirements</span></span>  
 <span data-ttu-id="e1748-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1748-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1748-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1748-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1748-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1748-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1748-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1748-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1748-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e1748-118">See also</span></span>

- [<span data-ttu-id="e1748-119">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="e1748-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="e1748-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e1748-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
