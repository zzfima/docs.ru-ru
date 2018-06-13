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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06ff8f0f13d7710d2d3d59aac4b5fdcadfe707be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418396"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="f03eb-102">Метод ICorDebugThread::GetUserState</span><span class="sxs-lookup"><span data-stu-id="f03eb-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="f03eb-103">Возвращает текущее состояние пользователя ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f03eb-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03eb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f03eb-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f03eb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f03eb-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="f03eb-106">[out] Указатель на побитовое сочетание значений перечисления CorDebugUserState, описывающих текущее состояние пользователя для данного потока.</span><span class="sxs-lookup"><span data-stu-id="f03eb-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f03eb-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f03eb-107">Remarks</span></span>  
 <span data-ttu-id="f03eb-108">Состояние пользователя потока — состояние потока анализируется отлаживаемой программы.</span><span class="sxs-lookup"><span data-stu-id="f03eb-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="f03eb-109">Для потока может быть задано несколько битов состояния.</span><span class="sxs-lookup"><span data-stu-id="f03eb-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f03eb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f03eb-110">Requirements</span></span>  
 <span data-ttu-id="f03eb-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f03eb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f03eb-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f03eb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f03eb-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f03eb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f03eb-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f03eb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
