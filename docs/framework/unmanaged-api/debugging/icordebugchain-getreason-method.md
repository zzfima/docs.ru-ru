---
title: Метод ICorDebugChain::GetReason
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- GetReason
helpviewer_keywords:
- GetReason method [.NET Framework debugging]
- ICorDebugChain::GetReason method [.NET Framework debugging]
ms.assetid: 9f9f62b9-113a-4a98-8f9b-b593cef27b03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d02a68e80e34be906e9fe09f3457a0f2214c6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405071"
---
# <a name="icordebugchaingetreason-method"></a><span data-ttu-id="f5bc1-102">Метод ICorDebugChain::GetReason</span><span class="sxs-lookup"><span data-stu-id="f5bc1-102">ICorDebugChain::GetReason Method</span></span>
<span data-ttu-id="f5bc1-103">Возвращает причину происхождения данной вызывающей цепи.</span><span class="sxs-lookup"><span data-stu-id="f5bc1-103">Gets the reason for the genesis of this calling chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5bc1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5bc1-104">Syntax</span></span>  
  
```  
HRESULT GetReason (  
    [out] CorDebugChainReason *pReason  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5bc1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5bc1-105">Parameters</span></span>  
 `pReason`  
 <span data-ttu-id="f5bc1-106">[out] Указатель на значение (побитовое сочетание) CorDebugChainReason перечисления, указывающее причину происхождения данной вызывающей цепи.</span><span class="sxs-lookup"><span data-stu-id="f5bc1-106">[out] A pointer to a value (a bitwise combination) of the CorDebugChainReason enumeration that indicates the reason for the genesis of this calling chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5bc1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f5bc1-107">Requirements</span></span>  
 <span data-ttu-id="f5bc1-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5bc1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5bc1-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5bc1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5bc1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5bc1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5bc1-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5bc1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
