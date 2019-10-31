---
title: Метод ICorDebugValue::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d6caa02333229bcd49f4c6ccf8b93265181a0b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137085"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="7aa95-102">Метод ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="7aa95-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="7aa95-103">Возвращает размер этого объекта "ICorDebugValue" в байтах.</span><span class="sxs-lookup"><span data-stu-id="7aa95-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7aa95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7aa95-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7aa95-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="7aa95-106">заполняет Размер данного объекта значения в байтах.</span><span class="sxs-lookup"><span data-stu-id="7aa95-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7aa95-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="7aa95-107">Remarks</span></span>  
 <span data-ttu-id="7aa95-108">Если типом значения является ссылочный тип, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="7aa95-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="7aa95-109">Метод `ICorDebugValue::GetSize` возвращает `COR_E_OVERFLOW` для объектов, размер которых превышает 4 ГБ на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="7aa95-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="7aa95-110">Используйте вместо него метод [ICorDebugValue3:: GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) для объектов, размер которых ПРЕВЫШАЕТ 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="7aa95-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa95-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7aa95-111">Requirements</span></span>  
 <span data-ttu-id="7aa95-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aa95-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa95-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7aa95-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7aa95-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7aa95-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7aa95-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa95-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa95-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7aa95-116">See also</span></span>

- [<span data-ttu-id="7aa95-117">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="7aa95-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
