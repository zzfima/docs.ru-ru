---
title: Метод ICorDebugEval::GetThread
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: 6a7d9465a454175b58bb7b9566d31f3c65420610
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085061"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="98e60-102">Метод ICorDebugEval::GetThread</span><span class="sxs-lookup"><span data-stu-id="98e60-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="98e60-103">Возвращает поток, в котором выполняется эта оценка или она будет выполнена.</span><span class="sxs-lookup"><span data-stu-id="98e60-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98e60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="98e60-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98e60-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="98e60-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="98e60-106">заполняет Указатель на адрес объекта ICorDebugThread, представляющего поток.</span><span class="sxs-lookup"><span data-stu-id="98e60-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98e60-107">Требования</span><span class="sxs-lookup"><span data-stu-id="98e60-107">Requirements</span></span>  
 <span data-ttu-id="98e60-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98e60-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e60-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98e60-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98e60-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98e60-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98e60-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98e60-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
