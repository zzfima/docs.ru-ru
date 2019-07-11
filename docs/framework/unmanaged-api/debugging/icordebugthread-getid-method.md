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
ms.openlocfilehash: 11e21e913e4749705ba6c7f91016be21b4de1712
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769967"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="17751-102">Метод ICorDebugThread::GetID</span><span class="sxs-lookup"><span data-stu-id="17751-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="17751-103">Возвращает идентификатор текущей операционной системы, активной части ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="17751-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17751-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17751-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17751-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="17751-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="17751-106">[out] Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="17751-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17751-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="17751-107">Remarks</span></span>  
 <span data-ttu-id="17751-108">Идентификатор операционной системы может измениться во время выполнения процесса и может быть другое значение для разных частей потока.</span><span class="sxs-lookup"><span data-stu-id="17751-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17751-109">Требования</span><span class="sxs-lookup"><span data-stu-id="17751-109">Requirements</span></span>  
 <span data-ttu-id="17751-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17751-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17751-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17751-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17751-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17751-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17751-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17751-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
