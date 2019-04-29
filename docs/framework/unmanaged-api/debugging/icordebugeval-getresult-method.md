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
ms.openlocfilehash: b8e7fcb4f44d6bdf6f18c93b1046b549331621a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667123"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="42e82-102">Метод ICorDebugEval::GetResult</span><span class="sxs-lookup"><span data-stu-id="42e82-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="42e82-103">Получает результаты этой оценки.</span><span class="sxs-lookup"><span data-stu-id="42e82-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e82-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42e82-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42e82-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="42e82-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="42e82-106">[out] Указатель на адрес объекта ICorDebugValue, представляющий результаты этой оценки, если оценка.</span><span class="sxs-lookup"><span data-stu-id="42e82-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42e82-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="42e82-107">Remarks</span></span>  
 <span data-ttu-id="42e82-108">`GetResult` Метод допустим только в том случае, после завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="42e82-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="42e82-109">Если оценка обычно `ppResult` указывает результаты.</span><span class="sxs-lookup"><span data-stu-id="42e82-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="42e82-110">Если он завершается с исключением, результатом является исключение.</span><span class="sxs-lookup"><span data-stu-id="42e82-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="42e82-111">Если оценка выполнялась для нового объекта, результатом является ссылка на новый объект.</span><span class="sxs-lookup"><span data-stu-id="42e82-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e82-112">Требования</span><span class="sxs-lookup"><span data-stu-id="42e82-112">Requirements</span></span>  
 <span data-ttu-id="42e82-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e82-114">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42e82-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42e82-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42e82-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42e82-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
