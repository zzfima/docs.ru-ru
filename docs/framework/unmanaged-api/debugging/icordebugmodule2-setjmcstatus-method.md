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
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129473"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="3cfe1-102">Метод ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="3cfe1-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="3cfe1-103">Задает для состояния Только мой код (JMC) всех методов всех классов в этом ICorDebugModule2 указанное значение, за исключением тех, которые заданы в массиве `pTokens`, для которого задается противоположное значение.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cfe1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cfe1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cfe1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cfe1-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="3cfe1-106">окне Задайте значение `true`, если код должен быть отлажен. в противном случае задайте значение `false`.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="3cfe1-107">[in] Размер массива `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="3cfe1-108">окне Массив значений `mdToken`, каждый из которых ссылается на метод, для которого в качестве его состояния JMC задано значение!`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cfe1-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="3cfe1-109">Remarks</span></span>  
 <span data-ttu-id="3cfe1-110">JMC состояние каждого метода, указанного в массиве `pTokens`, имеет значение, противоположное значению `bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="3cfe1-111">Состояние всех остальных методов в этом модуле задается как значение `bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="3cfe1-112">Метод `SetJMCStatus` удаляет все предыдущие параметры JMC в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="3cfe1-113">Метод `SetJMCStatus` возвращает значение S_OK HRESULT, если все функции заданы успешно.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="3cfe1-114">Он возвращает значение HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, если некоторые функции, помеченные `true`, не могут быть отлажены.</span><span class="sxs-lookup"><span data-stu-id="3cfe1-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cfe1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="3cfe1-115">Requirements</span></span>  
 <span data-ttu-id="3cfe1-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cfe1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cfe1-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cfe1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cfe1-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cfe1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cfe1-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cfe1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
