---
title: "Метод ICorDebugEval::GetResult"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.GetResult
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7379237c73d79d9e8c66112a101edadca357cb10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="499bb-102">Метод ICorDebugEval::GetResult</span><span class="sxs-lookup"><span data-stu-id="499bb-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="499bb-103">Получает результаты этой оценки.</span><span class="sxs-lookup"><span data-stu-id="499bb-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="499bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="499bb-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="499bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="499bb-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="499bb-106">[out] Указатель на адрес объекта ICorDebugValue, представляющий результаты этой оценки, если оценка.</span><span class="sxs-lookup"><span data-stu-id="499bb-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="499bb-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="499bb-107">Remarks</span></span>  
 <span data-ttu-id="499bb-108">`GetResult` Метод допустим только после завершения оценки.</span><span class="sxs-lookup"><span data-stu-id="499bb-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="499bb-109">Если оценка обычно `ppResult` указывает результаты.</span><span class="sxs-lookup"><span data-stu-id="499bb-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="499bb-110">Если он завершается с исключением, результатом является исключение.</span><span class="sxs-lookup"><span data-stu-id="499bb-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="499bb-111">Если оценка выполнялась для нового объекта, результатом является ссылка на новый объект.</span><span class="sxs-lookup"><span data-stu-id="499bb-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499bb-112">Требования</span><span class="sxs-lookup"><span data-stu-id="499bb-112">Requirements</span></span>  
 <span data-ttu-id="499bb-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="499bb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499bb-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="499bb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="499bb-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="499bb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="499bb-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499bb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
