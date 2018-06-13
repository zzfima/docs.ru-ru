---
title: Метод ICorDebugFunction::GetLocalVarSigToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a09741ed778436f1cb35d094885bd3effa813a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411598"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a><span data-ttu-id="5e2c3-102">Метод ICorDebugFunction::GetLocalVarSigToken</span><span class="sxs-lookup"><span data-stu-id="5e2c3-102">ICorDebugFunction::GetLocalVarSigToken Method</span></span>
<span data-ttu-id="5e2c3-103">Получает маркер метаданных для подписи локальной переменной функции, представленной данным экземпляром ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="5e2c3-103">Gets the metadata token for the local variable signature of the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e2c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e2c3-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e2c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e2c3-105">Parameters</span></span>  
 `pmdSig`  
 <span data-ttu-id="5e2c3-106">[out] Указатель на `mdSignature` маркер для подписи локальной переменной функции, или `mdSignatureNil`, если эта функция не имеет локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="5e2c3-106">[out] A pointer to the `mdSignature` token for the local variable signature of this function, or `mdSignatureNil`, if this function has no local variables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e2c3-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5e2c3-107">Requirements</span></span>  
 <span data-ttu-id="5e2c3-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e2c3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e2c3-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e2c3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e2c3-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e2c3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e2c3-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e2c3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
