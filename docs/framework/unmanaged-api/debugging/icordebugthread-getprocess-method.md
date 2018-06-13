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
ms.openlocfilehash: b41c7eeccad8b3f685c81e6afc23eaf19d862182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417616"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="125c0-102">Метод ICorDebugThread::GetProcess</span><span class="sxs-lookup"><span data-stu-id="125c0-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="125c0-103">Возвращает указатель на интерфейс для процесса, из которых ICorDebugThread эти формы.</span><span class="sxs-lookup"><span data-stu-id="125c0-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="125c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="125c0-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="125c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="125c0-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="125c0-106">[out] Указатель на адрес объекта интерфейса ICorDebugProcess, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="125c0-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="125c0-107">Требования</span><span class="sxs-lookup"><span data-stu-id="125c0-107">Requirements</span></span>  
 <span data-ttu-id="125c0-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="125c0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="125c0-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="125c0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="125c0-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="125c0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="125c0-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="125c0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
