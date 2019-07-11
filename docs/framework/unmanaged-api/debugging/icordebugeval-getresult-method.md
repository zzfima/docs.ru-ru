---
title: Метод ICorDebugEval::GetResult
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b12ba5ad5c85643d1f4c91585cf7abca210d22bd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752936"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="06d07-102">Метод ICorDebugEval::GetResult</span><span class="sxs-lookup"><span data-stu-id="06d07-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="06d07-103">Получает результаты этой оценки.</span><span class="sxs-lookup"><span data-stu-id="06d07-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06d07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06d07-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06d07-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="06d07-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="06d07-106">[out] Указатель на адрес объекта ICorDebugValue, представляющий результаты этой оценки, если оценка.</span><span class="sxs-lookup"><span data-stu-id="06d07-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06d07-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="06d07-107">Remarks</span></span>  
 <span data-ttu-id="06d07-108">`GetResult` Метод допустим только в том случае, после завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="06d07-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="06d07-109">Если оценка обычно `ppResult` указывает результаты.</span><span class="sxs-lookup"><span data-stu-id="06d07-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="06d07-110">Если он завершается с исключением, результатом является исключение.</span><span class="sxs-lookup"><span data-stu-id="06d07-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="06d07-111">Если оценка выполнялась для нового объекта, результатом является ссылка на новый объект.</span><span class="sxs-lookup"><span data-stu-id="06d07-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06d07-112">Требования</span><span class="sxs-lookup"><span data-stu-id="06d07-112">Requirements</span></span>  
 <span data-ttu-id="06d07-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06d07-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06d07-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06d07-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06d07-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06d07-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06d07-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06d07-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
