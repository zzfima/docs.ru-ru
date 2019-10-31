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
ms.openlocfilehash: ae0c23e3d48df6add8951a6d90029185a99bb323
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128834"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="fbada-102">Метод ICorDebugProcess::GetID</span><span class="sxs-lookup"><span data-stu-id="fbada-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="fbada-103">Возвращает идентификатор операционной системы (ОС) процесса.</span><span class="sxs-lookup"><span data-stu-id="fbada-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbada-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbada-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbada-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbada-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="fbada-106">заполняет Уникальный идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="fbada-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbada-107">Требования</span><span class="sxs-lookup"><span data-stu-id="fbada-107">Requirements</span></span>  
 <span data-ttu-id="fbada-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbada-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbada-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fbada-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fbada-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbada-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbada-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbada-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
