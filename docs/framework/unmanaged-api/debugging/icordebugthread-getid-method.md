---
title: Метод ICorDebugThread::GetID
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8eef616d51febd1b919e0a1936406551f441b98c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468979"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="d9d1c-102">Метод ICorDebugThread::GetID</span><span class="sxs-lookup"><span data-stu-id="d9d1c-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="d9d1c-103">Возвращает идентификатор текущей операционной системы, активной части ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="d9d1c-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9d1c-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9d1c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9d1c-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="d9d1c-106">[out] Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="d9d1c-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9d1c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d9d1c-107">Remarks</span></span>  
 <span data-ttu-id="d9d1c-108">Идентификатор операционной системы может измениться во время выполнения процесса и может быть другое значение для разных частей потока.</span><span class="sxs-lookup"><span data-stu-id="d9d1c-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9d1c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d9d1c-109">Requirements</span></span>  
 <span data-ttu-id="d9d1c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9d1c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9d1c-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9d1c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9d1c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9d1c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9d1c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9d1c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
