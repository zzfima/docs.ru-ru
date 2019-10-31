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
ms.openlocfilehash: 48d2af96b50bf77347256b3d5860405e460a09d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133451"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="a7373-102">Метод ICorDebugThread::GetID</span><span class="sxs-lookup"><span data-stu-id="a7373-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="a7373-103">Возвращает идентификатор текущей операционной системы активной части этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="a7373-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7373-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7373-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7373-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7373-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="a7373-106">заполняет Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="a7373-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7373-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a7373-107">Remarks</span></span>  
 <span data-ttu-id="a7373-108">Идентификатор операционной системы потенциально может изменяться во время выполнения процесса и может быть другим значением для разных частей потока.</span><span class="sxs-lookup"><span data-stu-id="a7373-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7373-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a7373-109">Requirements</span></span>  
 <span data-ttu-id="a7373-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7373-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7373-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7373-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7373-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7373-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7373-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7373-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
