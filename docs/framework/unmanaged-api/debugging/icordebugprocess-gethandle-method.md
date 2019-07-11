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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56f1dd892429724866182248b0c0413a7d2437cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766069"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="b2b97-102">Метод ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="b2b97-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="b2b97-103">Получает дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="b2b97-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2b97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2b97-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2b97-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="b2b97-106">[out] Указатель на `HPROCESS` это дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="b2b97-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2b97-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2b97-107">Remarks</span></span>  
 <span data-ttu-id="b2b97-108">Полученный дескриптор принадлежит интерфейсу отладки.</span><span class="sxs-lookup"><span data-stu-id="b2b97-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="b2b97-109">Отладчик должен его дубликаты перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="b2b97-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b97-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b2b97-110">Requirements</span></span>  
 <span data-ttu-id="b2b97-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2b97-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2b97-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2b97-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2b97-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2b97-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2b97-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2b97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
