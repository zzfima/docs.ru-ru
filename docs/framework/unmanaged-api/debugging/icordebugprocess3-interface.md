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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ccc45482f691d9950c641ef126a657052a280e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987705"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="5f9db-102">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="5f9db-102">ICorDebugProcess3 Interface</span></span>
<span data-ttu-id="5f9db-103">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="5f9db-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f9db-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5f9db-104">Methods</span></span>  
  
|<span data-ttu-id="5f9db-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5f9db-105">Method</span></span>|<span data-ttu-id="5f9db-106">Описание</span><span class="sxs-lookup"><span data-stu-id="5f9db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f9db-107">Метод SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="5f9db-107">SetEnableCustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="5f9db-108">Включает и отключает пользовательскими уведомлениями отладчика указанного типа.</span><span class="sxs-lookup"><span data-stu-id="5f9db-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f9db-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="5f9db-109">Remarks</span></span>  
 <span data-ttu-id="5f9db-110">Этот интерфейс логически расширяет интерфейс ICorDebugProcess и ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="5f9db-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f9db-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="5f9db-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f9db-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5f9db-112">Requirements</span></span>  
 <span data-ttu-id="5f9db-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f9db-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f9db-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f9db-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f9db-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f9db-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f9db-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f9db-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9db-117">См. также</span><span class="sxs-lookup"><span data-stu-id="5f9db-117">See also</span></span>

- [<span data-ttu-id="5f9db-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5f9db-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5f9db-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="5f9db-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
