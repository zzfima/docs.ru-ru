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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4bf3605331e6900fd890e49bb3f71f4ca4409c7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377597"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="94ec8-102">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="94ec8-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="94ec8-103">Расширяет интерфейс «ICorDebugValue» и «ICorDebugValue2» для обеспечения поддержки массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="94ec8-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94ec8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="94ec8-104">Methods</span></span>  
  
|<span data-ttu-id="94ec8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="94ec8-105">Method</span></span>|<span data-ttu-id="94ec8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="94ec8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94ec8-107">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="94ec8-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="94ec8-108">Получает размер в байтах, это `ICorDebugValue3` объекта.</span><span class="sxs-lookup"><span data-stu-id="94ec8-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94ec8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="94ec8-109">Remarks</span></span>  
 <span data-ttu-id="94ec8-110">[ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) метод возвращает размер объекта, в диапазоне от 0 до 2 147 483 647 байт.</span><span class="sxs-lookup"><span data-stu-id="94ec8-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="94ec8-111">В .NET Framework 4.5 размер массивов может превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="94ec8-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="94ec8-112">`ICorDebugValue3` Интерфейса позволяет определить размер этих массивов.</span><span class="sxs-lookup"><span data-stu-id="94ec8-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94ec8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="94ec8-113">Requirements</span></span>  
 <span data-ttu-id="94ec8-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94ec8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94ec8-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94ec8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94ec8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94ec8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94ec8-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94ec8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94ec8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="94ec8-118">See also</span></span>

- [<span data-ttu-id="94ec8-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="94ec8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="94ec8-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="94ec8-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
