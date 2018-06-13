---
title: Метод ICorDebugChain::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f050a3d9d37e43713c40896fb162bcf9932c6512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403374"
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="108b0-102">Метод ICorDebugChain::GetCallee</span><span class="sxs-lookup"><span data-stu-id="108b0-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="108b0-103">Получает цепь, вызванной этой цепи.</span><span class="sxs-lookup"><span data-stu-id="108b0-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="108b0-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="108b0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="108b0-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="108b0-106">[out] Указатель на адрес объекта ICorDebugChain, который представляет вызванная цепь.</span><span class="sxs-lookup"><span data-stu-id="108b0-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="108b0-107">Если эта цепочка выполняемый в текущий момент (то есть, если эта цепь не ожидает вызванной цепью для возврата), `ppChain` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="108b0-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="108b0-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="108b0-108">Remarks</span></span>  
 <span data-ttu-id="108b0-109">Данная цепь будет ожидать вызванная цепь для возврата свое выполнение.</span><span class="sxs-lookup"><span data-stu-id="108b0-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="108b0-110">Вызванная цепь может находиться в другом потоке в случае маршалируется вызовы между потоками.</span><span class="sxs-lookup"><span data-stu-id="108b0-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108b0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="108b0-111">Requirements</span></span>  
 <span data-ttu-id="108b0-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="108b0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="108b0-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="108b0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="108b0-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="108b0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="108b0-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="108b0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
