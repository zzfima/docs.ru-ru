---
title: Метод ICorDebugStepper2::SetJMC
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 129bf04a097b2019b080f813bf049d41b501f8fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663873"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="02207-102">Метод ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="02207-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="02207-103">Задает значение, указывающее ли ICorDebugStepper проходит только через код, который создается разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="02207-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="02207-104">Этот процесс также известен отладка, как только собственного кода (JMC).</span><span class="sxs-lookup"><span data-stu-id="02207-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02207-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02207-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02207-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="02207-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="02207-107">[in] Значение `true` к шагу только через код, который является автором разработчик приложения; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="02207-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02207-108">Требования</span><span class="sxs-lookup"><span data-stu-id="02207-108">Requirements</span></span>  
 <span data-ttu-id="02207-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02207-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02207-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02207-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02207-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02207-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02207-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02207-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
