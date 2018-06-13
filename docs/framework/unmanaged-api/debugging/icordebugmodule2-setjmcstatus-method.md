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
ms.openlocfilehash: a56b5c31c26dbe5c5371fdb7a10c13ad11847117
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419476"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="0314a-102">Метод ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="0314a-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="0314a-103">Задает состояние "только мой код (") все методы для всех классов в этом ICorDebugModule2 указанное значение, за исключением тех, в `pTokens` массив, который задает его значение с противоположным.</span><span class="sxs-lookup"><span data-stu-id="0314a-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0314a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0314a-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0314a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0314a-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="0314a-106">[in] Значение `true` при код отладки; в противном случае значение `false`.</span><span class="sxs-lookup"><span data-stu-id="0314a-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="0314a-107">[in] Размер массива `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="0314a-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="0314a-108">[in] Массив `mdToken` значений, каждое из которых ссылается на метод, который будет в состоянии его JMC!`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="0314a-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0314a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0314a-109">Remarks</span></span>  
 <span data-ttu-id="0314a-110">Состояние JMC каждого метода, указанного в `pTokens` массива равен противоположность `bIsJustMycode` значение.</span><span class="sxs-lookup"><span data-stu-id="0314a-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="0314a-111">Присвоено состояние всех методов в этом модуле `bIsJustMycode` значение.</span><span class="sxs-lookup"><span data-stu-id="0314a-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="0314a-112">`SetJMCStatus` Метод удаляет все предыдущие настройки JMC в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="0314a-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="0314a-113">`SetJMCStatus` Метод возвращает значение HRESULT S_OK, если все функции успешно установлено.</span><span class="sxs-lookup"><span data-stu-id="0314a-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="0314a-114">Он возвращает HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, если некоторые функции, помеченные `true` не являются доступными для отладки.</span><span class="sxs-lookup"><span data-stu-id="0314a-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0314a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0314a-115">Requirements</span></span>  
 <span data-ttu-id="0314a-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0314a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0314a-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0314a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0314a-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0314a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0314a-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0314a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
