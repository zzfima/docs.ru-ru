---
title: Метод ICorDebugModule::EnableJITDebugging
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableJITDebugging
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type:
- apiref
ms.openlocfilehash: da532ee1b5909a68bedbb9e6f6c96333e88002a8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109726"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="f025e-102">Метод ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="f025e-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="f025e-103">Определяет, сохраняет ли JIT-компилятор сведения об отладке для методов в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="f025e-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f025e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f025e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f025e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f025e-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="f025e-106">окне Присвойте этому параметру значение `true`, чтобы разрешить JIT-компилятору сохранять сведения о сопоставлении между версией MSIL и версией каждого метода в этом модуле, скомпилированном по требованию.</span><span class="sxs-lookup"><span data-stu-id="f025e-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="f025e-107">окне Задайте для этого параметра значение `true`, чтобы JIT-компилятор создавал код с определенными оптимизацией JIT для отладки.</span><span class="sxs-lookup"><span data-stu-id="f025e-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f025e-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="f025e-108">Remarks</span></span>  
 <span data-ttu-id="f025e-109">JIT-отладка включается по умолчанию для всех модулей, загружаемых при активном отладчике.</span><span class="sxs-lookup"><span data-stu-id="f025e-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="f025e-110">Программное включение или отключение параметров переопределяет глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="f025e-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f025e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f025e-111">Requirements</span></span>  
 <span data-ttu-id="f025e-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f025e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f025e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f025e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f025e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f025e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f025e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f025e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
