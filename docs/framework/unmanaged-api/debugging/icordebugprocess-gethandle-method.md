---
title: Метод ICorDebugProcess::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: e4061580d59b0cf2a6e6e481d5242005e9452caf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128873"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="96394-102">Метод ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="96394-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="96394-103">Возвращает маркер процесса.</span><span class="sxs-lookup"><span data-stu-id="96394-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96394-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96394-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96394-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96394-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="96394-106">заполняет Указатель на `HPROCESS`, который является обработчиком процесса.</span><span class="sxs-lookup"><span data-stu-id="96394-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96394-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="96394-107">Remarks</span></span>  
 <span data-ttu-id="96394-108">Полученный обработчик принадлежит интерфейсу отладки.</span><span class="sxs-lookup"><span data-stu-id="96394-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="96394-109">Отладчик должен дублировать этот обработчик перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="96394-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96394-110">Требования</span><span class="sxs-lookup"><span data-stu-id="96394-110">Requirements</span></span>  
 <span data-ttu-id="96394-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96394-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96394-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96394-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96394-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96394-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96394-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96394-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
