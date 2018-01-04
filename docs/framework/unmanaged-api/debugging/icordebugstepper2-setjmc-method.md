---
title: "Метод ICorDebugStepper2::SetJMC"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper2.SetJMC
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fbbe0d3e42df073a5718ca037b44f6f2f31ec23
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="2200e-102">Метод ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="2200e-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="2200e-103">Задает значение, указывающее, является ли ICorDebugStepper пошаговое выполнение только код, созданный разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="2200e-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="2200e-104">Этот процесс также известен отладка как только собственного кода (JMC).</span><span class="sxs-lookup"><span data-stu-id="2200e-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2200e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2200e-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2200e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2200e-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="2200e-107">[in] Значение `true` шагу только через код, созданный разработчиком приложения; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2200e-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2200e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="2200e-108">Requirements</span></span>  
 <span data-ttu-id="2200e-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2200e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2200e-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2200e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2200e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2200e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2200e-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2200e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
