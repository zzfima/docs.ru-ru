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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71722293bfb80a7e57393916560f922d970ea2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415646"
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="5040e-102">Метод ICorDebugModule::EnableJITDebugging</span><span class="sxs-lookup"><span data-stu-id="5040e-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="5040e-103">Определяет, сохраняет ли компилятор just-in-time (JIT), сведения об отладке для методов в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="5040e-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5040e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5040e-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5040e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5040e-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="5040e-106">[in] Это значение равно `true` для включения JIT-компилятором для сохранения сведений о сопоставлении между версией Microsoft промежуточного языка MSIL и версии JIT-компиляции каждого метода в данном модуле.</span><span class="sxs-lookup"><span data-stu-id="5040e-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="5040e-107">[in] Это значение равно `true` для включения JIT-компилятору создавать код с помощью определенные оптимизации конкретных JIT-компилятора для отладки.</span><span class="sxs-lookup"><span data-stu-id="5040e-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5040e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5040e-108">Remarks</span></span>  
 <span data-ttu-id="5040e-109">JIT-отладка включена по умолчанию для всех модулей, загруженных при активном отладчик.</span><span class="sxs-lookup"><span data-stu-id="5040e-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="5040e-110">Программное Включение или отключение параметров переопределяет глобальные настройки.</span><span class="sxs-lookup"><span data-stu-id="5040e-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5040e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5040e-111">Requirements</span></span>  
 <span data-ttu-id="5040e-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5040e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5040e-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5040e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5040e-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5040e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5040e-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5040e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
