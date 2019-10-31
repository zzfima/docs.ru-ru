---
title: Метод ICorDebugThread::GetUserState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: f3511ff5ee9b9221037c64a5e17d61f6bf52e5f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133419"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="8d69b-102">Метод ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="8d69b-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="8d69b-103">Возвращает текущее пользовательское состояние этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8d69b-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d69b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d69b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d69b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d69b-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="8d69b-106">заполняет Указатель на побитовую комбинацию значений перечисления Кордебугусерстате, описывающих текущее пользовательское состояние этого потока.</span><span class="sxs-lookup"><span data-stu-id="8d69b-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d69b-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="8d69b-107">Remarks</span></span>  
 <span data-ttu-id="8d69b-108">Пользовательское состояние потока — это состояние потока, которое проверяется отлаживаемой программой.</span><span class="sxs-lookup"><span data-stu-id="8d69b-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="8d69b-109">Для потока может быть задано несколько битов состояния.</span><span class="sxs-lookup"><span data-stu-id="8d69b-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d69b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8d69b-110">Requirements</span></span>  
 <span data-ttu-id="8d69b-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d69b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d69b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d69b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d69b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d69b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d69b-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d69b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
