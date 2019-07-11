---
title: Метод ICorDebugProcess::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5cbdd19fa14a41d8bd2eadec80dbafcea7b720d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766432"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="f28af-102">Метод ICorDebugProcess::GetThread</span><span class="sxs-lookup"><span data-stu-id="f28af-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="f28af-103">Возвращает поток этот процесс, который имеет идентификатор потока операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="f28af-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f28af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f28af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f28af-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f28af-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="f28af-106">[in] Идентификатор потока, требуется получить потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="f28af-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="f28af-107">[out] Указатель на адрес ICorDebugThread объект, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="f28af-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f28af-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f28af-108">Requirements</span></span>  
 <span data-ttu-id="f28af-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f28af-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f28af-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f28af-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f28af-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f28af-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f28af-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f28af-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
