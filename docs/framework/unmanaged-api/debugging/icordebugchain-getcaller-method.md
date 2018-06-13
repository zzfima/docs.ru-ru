---
title: Метод ICorDebugChain::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405147"
---
# <a name="icordebugchaingetcaller-method"></a><span data-ttu-id="9a13d-102">Метод ICorDebugChain::GetCaller</span><span class="sxs-lookup"><span data-stu-id="9a13d-102">ICorDebugChain::GetCaller Method</span></span>
<span data-ttu-id="9a13d-103">Получает цепь, вызвавшую данную цепь.</span><span class="sxs-lookup"><span data-stu-id="9a13d-103">Gets the chain that called this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a13d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a13d-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a13d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a13d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="9a13d-106">[out] Указатель на адрес объекта ICorDebugChain, который представляет цепочки вызовов.</span><span class="sxs-lookup"><span data-stu-id="9a13d-106">[out] A pointer to the address of an ICorDebugChain object that represents the calling chain.</span></span>  
  
 <span data-ttu-id="9a13d-107">Если эта цепь была вызвана спонтанно (как это может произойти, если эта цепочка или отладчиком инициализирован стек вызовов), `ppChain` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="9a13d-107">If this chain was spontaneously called (as would be the case if this chain or the debugger initialized the call stack), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a13d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a13d-108">Remarks</span></span>  
 <span data-ttu-id="9a13d-109">Цепочки вызовов может быть в другом потоке, если вызов был маршалинг между потоками.</span><span class="sxs-lookup"><span data-stu-id="9a13d-109">The calling chain may be on a different thread, if the call was marshaled across threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a13d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9a13d-110">Requirements</span></span>  
 <span data-ttu-id="9a13d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a13d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a13d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a13d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a13d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a13d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a13d-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a13d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
