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
ms.openlocfilehash: 52bfe669d3b078657916554255a11cecfc07d484
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085092"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="51b6d-102">Метод ICorDebugEval::GetResult</span><span class="sxs-lookup"><span data-stu-id="51b6d-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="51b6d-103">Возвращает результаты этой оценки.</span><span class="sxs-lookup"><span data-stu-id="51b6d-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51b6d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51b6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51b6d-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="51b6d-106">заполняет Указатель на адрес объекта ICorDebugValue, который представляет результаты этой оценки, если вычисление завершается нормально.</span><span class="sxs-lookup"><span data-stu-id="51b6d-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51b6d-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="51b6d-107">Remarks</span></span>  
 <span data-ttu-id="51b6d-108">Метод `GetResult` действителен только после завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="51b6d-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="51b6d-109">Если вычисление завершается нормально, `ppResult` указывает результаты.</span><span class="sxs-lookup"><span data-stu-id="51b6d-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="51b6d-110">Если оно завершается с исключением, результатом является исключение.</span><span class="sxs-lookup"><span data-stu-id="51b6d-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="51b6d-111">Если вычисление выполнялось для нового объекта, результатом является ссылка на новый объект.</span><span class="sxs-lookup"><span data-stu-id="51b6d-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51b6d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="51b6d-112">Requirements</span></span>  
 <span data-ttu-id="51b6d-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51b6d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51b6d-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51b6d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51b6d-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51b6d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51b6d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51b6d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
