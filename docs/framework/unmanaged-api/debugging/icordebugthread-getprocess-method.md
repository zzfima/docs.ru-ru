---
title: Метод ICorDebugThread::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad87b6552df25926b5b4184b7884c1d444c4f1be
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769069"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="1fcdd-102">Метод ICorDebugThread::GetProcess</span><span class="sxs-lookup"><span data-stu-id="1fcdd-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="1fcdd-103">Получает указатель интерфейса на процесс, из которых ICorDebugThread эти формы.</span><span class="sxs-lookup"><span data-stu-id="1fcdd-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fcdd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fcdd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1fcdd-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="1fcdd-106">[out] Указатель на адрес объекта интерфейса ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="1fcdd-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fcdd-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1fcdd-107">Requirements</span></span>  
 <span data-ttu-id="1fcdd-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fcdd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fcdd-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fcdd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fcdd-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fcdd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fcdd-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fcdd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
