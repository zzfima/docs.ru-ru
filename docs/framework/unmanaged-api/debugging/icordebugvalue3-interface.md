---
title: Интерфейс ICorDebugValue3
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
ms.openlocfilehash: 1f46866a1b975455acd294221e38ef3b4c358660
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140206"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="f9c03-102">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="f9c03-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="f9c03-103">Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="f9c03-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9c03-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f9c03-104">Methods</span></span>  
  
|<span data-ttu-id="f9c03-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f9c03-105">Method</span></span>|<span data-ttu-id="f9c03-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f9c03-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f9c03-107">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="f9c03-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="f9c03-108">Возвращает размер данного объекта `ICorDebugValue3` в байтах.</span><span class="sxs-lookup"><span data-stu-id="f9c03-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9c03-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="f9c03-109">Remarks</span></span>  
 <span data-ttu-id="f9c03-110">Метод [ICorDebugValue::](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) GetBytes возвращает размер объекта в диапазоне от 0 до 2 147 483 647 байт.</span><span class="sxs-lookup"><span data-stu-id="f9c03-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="f9c03-111">В .NET Framework 4,5 размер массивов может превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="f9c03-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="f9c03-112">Интерфейс `ICorDebugValue3` позволяет определить размер этих массивов.</span><span class="sxs-lookup"><span data-stu-id="f9c03-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9c03-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f9c03-113">Requirements</span></span>  
 <span data-ttu-id="f9c03-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9c03-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9c03-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9c03-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9c03-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9c03-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9c03-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9c03-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c03-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f9c03-118">See also</span></span>

- [<span data-ttu-id="f9c03-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f9c03-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f9c03-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="f9c03-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
