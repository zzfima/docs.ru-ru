---
title: Метод ICorDebugProcess::GetID
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d9239ccfe8ce08e5b50b762a6fede11ab8a439b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495719"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="62785-102">Метод ICorDebugProcess::GetID</span><span class="sxs-lookup"><span data-stu-id="62785-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="62785-103">Получает идентификатор процесса операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="62785-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62785-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62785-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62785-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62785-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="62785-106">[out] Уникальный идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="62785-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62785-107">Требования</span><span class="sxs-lookup"><span data-stu-id="62785-107">Requirements</span></span>  
 <span data-ttu-id="62785-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62785-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62785-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62785-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62785-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62785-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62785-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62785-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
