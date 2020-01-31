---
title: Интерфейс ICorDebugObjectEnum
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: 0526c050bcf1316eccf2c756a404fbb971e6d7d0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792743"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="7ab52-102">Интерфейс ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="7ab52-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="7ab52-103">Реализует методы ICorDebugEnum и перечисляет массивы объектов по их относительным виртуальным адресам (RVA).</span><span class="sxs-lookup"><span data-stu-id="7ab52-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ab52-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7ab52-104">Methods</span></span>  
  
|<span data-ttu-id="7ab52-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7ab52-105">Method</span></span>|<span data-ttu-id="7ab52-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7ab52-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ab52-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="7ab52-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="7ab52-108">Возвращает RVA указанного числа объектов из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="7ab52-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ab52-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="7ab52-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ab52-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="7ab52-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab52-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7ab52-111">Requirements</span></span>  
 <span data-ttu-id="7ab52-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab52-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab52-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ab52-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ab52-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ab52-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ab52-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab52-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab52-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="7ab52-116">See also</span></span>

- [<span data-ttu-id="7ab52-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7ab52-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
