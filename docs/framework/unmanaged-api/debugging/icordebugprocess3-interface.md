---
title: Интерфейс ICorDebugProcess3
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
ms.openlocfilehash: 28d1d426276e9654c2122f03fb64735b7e67f44f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792475"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="6f907-102">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="6f907-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="6f907-103">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="6f907-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f907-104">Методы</span><span class="sxs-lookup"><span data-stu-id="6f907-104">Methods</span></span>  
  
|<span data-ttu-id="6f907-105">Метод</span><span class="sxs-lookup"><span data-stu-id="6f907-105">Method</span></span>|<span data-ttu-id="6f907-106">Описание</span><span class="sxs-lookup"><span data-stu-id="6f907-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f907-107">Метод SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="6f907-107">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="6f907-108">Включает и отключает настраиваемые уведомления отладчика указанного типа.</span><span class="sxs-lookup"><span data-stu-id="6f907-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f907-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="6f907-109">Remarks</span></span>  
 <span data-ttu-id="6f907-110">Этот интерфейс логически расширяет интерфейсы ICorDebugProcess и ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="6f907-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f907-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="6f907-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f907-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6f907-112">Requirements</span></span>  
 <span data-ttu-id="6f907-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f907-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f907-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f907-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f907-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f907-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f907-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f907-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f907-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="6f907-117">See also</span></span>

- [<span data-ttu-id="6f907-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6f907-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6f907-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="6f907-119">Debugging</span></span>](index.md)
