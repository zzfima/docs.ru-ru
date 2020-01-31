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
ms.openlocfilehash: 3d26ddb6d89af60acf6dc1214b0423ba75e488ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791170"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="e6c21-102">Метод ICorDebugValue::GetSize</span><span class="sxs-lookup"><span data-stu-id="e6c21-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="e6c21-103">Возвращает размер этого объекта "ICorDebugValue" в байтах.</span><span class="sxs-lookup"><span data-stu-id="e6c21-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6c21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6c21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6c21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6c21-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="e6c21-106">заполняет Размер данного объекта значения в байтах.</span><span class="sxs-lookup"><span data-stu-id="e6c21-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6c21-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="e6c21-107">Remarks</span></span>  
 <span data-ttu-id="e6c21-108">Если типом значения является ссылочный тип, этот метод возвращает размер указателя, а не размер объекта.</span><span class="sxs-lookup"><span data-stu-id="e6c21-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="e6c21-109">Метод `ICorDebugValue::GetSize` возвращает `COR_E_OVERFLOW` для объектов, размер которых превышает 4 ГБ на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="e6c21-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="e6c21-110">Используйте вместо него метод [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) для объектов, размер которых ПРЕВЫШАЕТ 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="e6c21-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6c21-111">Требования</span><span class="sxs-lookup"><span data-stu-id="e6c21-111">Requirements</span></span>  
 <span data-ttu-id="e6c21-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6c21-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6c21-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6c21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6c21-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6c21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6c21-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6c21-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6c21-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6c21-116">See also</span></span>

- [<span data-ttu-id="e6c21-117">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="e6c21-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
