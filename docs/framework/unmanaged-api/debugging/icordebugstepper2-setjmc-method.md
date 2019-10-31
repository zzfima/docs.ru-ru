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
ms.openlocfilehash: 6c076dd2912a22e4f9492492a2d7a9fb73db88e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139041"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="f4eed-102">Метод ICorDebugStepper2::SetJMC</span><span class="sxs-lookup"><span data-stu-id="f4eed-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="f4eed-103">Задает значение, указывающее, следует ли выполнить шаги для этого параметра ICorDebugStepper только с помощью кода, созданного разработчиком приложения.</span><span class="sxs-lookup"><span data-stu-id="f4eed-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="f4eed-104">Этот процесс также известен как отладка "только мой код" (JMC).</span><span class="sxs-lookup"><span data-stu-id="f4eed-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4eed-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4eed-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4eed-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4eed-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="f4eed-107">окне Присвойте параметру значение `true` для шага только с помощью кода, созданного разработчиком приложения; в противном случае задайте значение `false`.</span><span class="sxs-lookup"><span data-stu-id="f4eed-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4eed-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f4eed-108">Requirements</span></span>  
 <span data-ttu-id="f4eed-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4eed-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4eed-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4eed-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4eed-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4eed-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4eed-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4eed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
