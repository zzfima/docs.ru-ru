---
title: "Метод ICorDebugModule2::SetJMCStatus"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca4b53acc69d0a56b94526de0c3b16fd1abde077
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="6c0d8-102">Метод ICorDebugModule2::SetJMCStatus</span><span class="sxs-lookup"><span data-stu-id="6c0d8-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="6c0d8-103">Задает состояние "только мой код (") все методы для всех классов в этом ICorDebugModule2 указанное значение, за исключением тех, в `pTokens` массив, который задает его значение с противоположным.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c0d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c0d8-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c0d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c0d8-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="6c0d8-106">[in] Значение `true` при код отладки; в противном случае значение `false`.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="6c0d8-107">[in] Размер массива `pTokens`.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="6c0d8-108">[in] Массив `mdToken` значений, каждое из которых ссылается на метод, который будет в состоянии его JMC!`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c0d8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c0d8-109">Remarks</span></span>  
 <span data-ttu-id="6c0d8-110">Состояние JMC каждого метода, указанного в `pTokens` массива равен противоположность `bIsJustMycode` значение.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="6c0d8-111">Присвоено состояние всех методов в этом модуле `bIsJustMycode` значение.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="6c0d8-112">`SetJMCStatus` Метод удаляет все предыдущие настройки JMC в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="6c0d8-113">`SetJMCStatus` Метод возвращает значение HRESULT S_OK, если все функции успешно установлено.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="6c0d8-114">Он возвращает HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, если некоторые функции, помеченные `true` не являются доступными для отладки.</span><span class="sxs-lookup"><span data-stu-id="6c0d8-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c0d8-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6c0d8-115">Requirements</span></span>  
 <span data-ttu-id="6c0d8-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c0d8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c0d8-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c0d8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c0d8-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c0d8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c0d8-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c0d8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
