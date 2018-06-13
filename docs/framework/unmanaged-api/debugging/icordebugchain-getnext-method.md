---
title: Метод ICorDebugChain::GetNext
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetNext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetNext
helpviewer_keywords:
- GetNext method [.NET Framework debugging]
- ICorDebugChain::GetNext method [.NET Framework debugging]
ms.assetid: 8d9744a5-e08b-4ab2-9855-5c22711cc1e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 839052b72d908e48a4b6f88dab05ec3c3d575d65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405415"
---
# <a name="icordebugchaingetnext-method"></a><span data-ttu-id="4f07c-102">Метод ICorDebugChain::GetNext</span><span class="sxs-lookup"><span data-stu-id="4f07c-102">ICorDebugChain::GetNext Method</span></span>
<span data-ttu-id="4f07c-103">Получает следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="4f07c-103">Gets the next chain of frames for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f07c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f07c-104">Syntax</span></span>  
  
```  
HRESULT GetNext (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f07c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f07c-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="4f07c-106">[out] Указатель на адрес объекта ICorDebugChain, который представляет следующую цепь кадров для потока.</span><span class="sxs-lookup"><span data-stu-id="4f07c-106">[out] A pointer to the address of an ICorDebugChain object that represents the next chain of frames for the thread.</span></span> <span data-ttu-id="4f07c-107">Если эта цепь является последней, `ppChain` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="4f07c-107">If this chain is the last chain, `ppChain` is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f07c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4f07c-108">Requirements</span></span>  
 <span data-ttu-id="4f07c-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f07c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f07c-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f07c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f07c-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f07c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f07c-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f07c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
