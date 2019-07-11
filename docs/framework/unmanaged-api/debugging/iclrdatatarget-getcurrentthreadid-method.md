---
title: Метод ICLRDataTarget::GetCurrentThreadID
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45a409bda8861701e68d3ea1a956a4c35ce88ddd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738779"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="7d4ce-102">Метод ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="7d4ce-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="7d4ce-103">Получает идентификатор операционной системы для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="7d4ce-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d4ce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d4ce-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d4ce-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d4ce-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="7d4ce-106">[out] Указатель на идентификатор операционной системы, текущего потока для целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="7d4ce-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d4ce-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d4ce-107">Remarks</span></span>  
 <span data-ttu-id="7d4ce-108">Если нет текущего потока для целевого процесса, `GetCurrentThreadID` может произойти сбой метода.</span><span class="sxs-lookup"><span data-stu-id="7d4ce-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d4ce-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7d4ce-109">Requirements</span></span>  
 <span data-ttu-id="7d4ce-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d4ce-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d4ce-111">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="7d4ce-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7d4ce-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d4ce-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d4ce-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d4ce-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d4ce-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7d4ce-114">See also</span></span>

- [<span data-ttu-id="7d4ce-115">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="7d4ce-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
