---
title: "Метод ICorDebugFunction::GetLocalVarSigToken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetLocalVarSigToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfd2998393429d26f4670edfeae44b83893f479d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="8a84a-102">Метод ICorDebugFunction::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="8a84a-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="8a84a-103">Получает маркер метаданных для подписи локальной переменной функции, представленной данным экземпляром ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="8a84a-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a84a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a84a-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a84a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8a84a-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="8a84a-106">[out] Указатель на `mdSignature` маркер для подписи локальной переменной функции, или `mdSignatureNil`, если эта функция не имеет локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="8a84a-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a84a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8a84a-107">Requirements</span></span>  
 <span data-ttu-id="8a84a-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a84a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a84a-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a84a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a84a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a84a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a84a-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a84a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
