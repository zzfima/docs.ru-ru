---
title: Метод ICorDebugModule2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d20c640d6a6a43b7bde4c7d46df470c7bc8c5aa2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499528"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="96b64-102">Метод ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="96b64-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="96b64-103">Задает состояние "только мой код (") все методы для всех классов в этом ICorDebugModule2 указанное значение, за исключением тех, в `pTokens` массив, который задает противоположное значение.</span><span class="sxs-lookup"><span data-stu-id="96b64-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96b64-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96b64-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96b64-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="96b64-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="96b64-106">[in] Значение `true` Если код является отладки; в противном случае, значение `false`.</span><span class="sxs-lookup"><span data-stu-id="96b64-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="96b64-107">[in] Размер массива `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="96b64-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="96b64-108">[in] Массив `mdToken` значений, каждое из которых ссылается на метод, который будет иметь состоянием JMC!`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="96b64-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96b64-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="96b64-109">Remarks</span></span>  
 <span data-ttu-id="96b64-110">Состояние JMC каждого метода, который указан в `pTokens` массива имеет значение противоположностью `bIsJustMycode` значение.</span><span class="sxs-lookup"><span data-stu-id="96b64-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="96b64-111">Присвоено состояние всех методов в этом модуле `bIsJustMycode` значение.</span><span class="sxs-lookup"><span data-stu-id="96b64-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="96b64-112">`SetJMCStatus` Метод стирает все предыдущие параметры JMC в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="96b64-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="96b64-113">`SetJMCStatus` Метод возвращает значение S_OK HRESULT, если успешно заданы все функции.</span><span class="sxs-lookup"><span data-stu-id="96b64-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="96b64-114">Он возвращает HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, если некоторые функции, которые помечены `true` не подлежит отладке.</span><span class="sxs-lookup"><span data-stu-id="96b64-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96b64-115">Требования</span><span class="sxs-lookup"><span data-stu-id="96b64-115">Requirements</span></span>  
 <span data-ttu-id="96b64-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96b64-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96b64-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96b64-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96b64-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96b64-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96b64-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96b64-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
