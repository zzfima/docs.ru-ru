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
ms.openlocfilehash: 008f945b5301894261ce1529cbd915dd614b919d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418959"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="0482e-102">Метод ICorDebugProcess::GetThread</span><span class="sxs-lookup"><span data-stu-id="0482e-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="0482e-103">Возвращает поток этот процесс, который имеет идентификатор потока операционной системы (ОС)</span><span class="sxs-lookup"><span data-stu-id="0482e-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0482e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0482e-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0482e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0482e-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="0482e-106">[in] Идентификатор потока должны быть получены потока операционной системы.</span><span class="sxs-lookup"><span data-stu-id="0482e-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="0482e-107">[out] Указатель на адрес объекта, представляющего поток ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0482e-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0482e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0482e-108">Requirements</span></span>  
 <span data-ttu-id="0482e-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0482e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0482e-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0482e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0482e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0482e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0482e-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0482e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
