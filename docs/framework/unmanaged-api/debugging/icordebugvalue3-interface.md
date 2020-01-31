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
ms.openlocfilehash: 5fa042223e47961dad0a6799ab8ca999ef76e285
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791084"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="fd2e8-102">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="fd2e8-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="fd2e8-103">Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, размер которых превышает 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="fd2e8-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd2e8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fd2e8-104">Methods</span></span>  
  
|<span data-ttu-id="fd2e8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fd2e8-105">Method</span></span>|<span data-ttu-id="fd2e8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fd2e8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd2e8-107">Метод GetSize64</span><span class="sxs-lookup"><span data-stu-id="fd2e8-107">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)|<span data-ttu-id="fd2e8-108">Возвращает размер данного объекта `ICorDebugValue3` в байтах.</span><span class="sxs-lookup"><span data-stu-id="fd2e8-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd2e8-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="fd2e8-109">Remarks</span></span>  
 <span data-ttu-id="fd2e8-110">Метод [ICorDebugValue::](icordebugvalue3-getsize64-method.md) GetBytes возвращает размер объекта в диапазоне от 0 до 2 147 483 647 байт.</span><span class="sxs-lookup"><span data-stu-id="fd2e8-110">The [ICorDebugValue::GetSize](icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="fd2e8-111">В .NET Framework 4,5 размер массивов может превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="fd2e8-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="fd2e8-112">Интерфейс `ICorDebugValue3` позволяет определить размер этих массивов.</span><span class="sxs-lookup"><span data-stu-id="fd2e8-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd2e8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fd2e8-113">Requirements</span></span>  
 <span data-ttu-id="fd2e8-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd2e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd2e8-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd2e8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd2e8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd2e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd2e8-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd2e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2e8-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fd2e8-118">See also</span></span>

- [<span data-ttu-id="fd2e8-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fd2e8-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fd2e8-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="fd2e8-120">Debugging</span></span>](index.md)
