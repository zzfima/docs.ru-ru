---
title: "Метод ICorDebugFunction::CreateBreakpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.CreateBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0565f7ad5e57ad63607b1a28e3ecb26965afd974
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="08abb-102">Метод ICorDebugFunction::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="08abb-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="08abb-103">Создает точку останова в начале этой функции.</span><span class="sxs-lookup"><span data-stu-id="08abb-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08abb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08abb-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08abb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08abb-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="08abb-106">[out] Указатель на адрес объекта ICorDebugFunctionBreakpoint, который представляет новую точку останова для функции.</span><span class="sxs-lookup"><span data-stu-id="08abb-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08abb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="08abb-107">Requirements</span></span>  
 <span data-ttu-id="08abb-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08abb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08abb-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08abb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08abb-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08abb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08abb-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08abb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
