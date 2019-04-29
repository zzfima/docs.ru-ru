---
title: Метод ICorDebugProcess2::GetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a59067f72005e87152680e4f990fc74e4acdaa9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948945"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="e7adc-102">Метод ICorDebugProcess2::GetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="e7adc-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="e7adc-103">Получает текущий компилятор общеязыковой среды выполнения (CLR) использует для выбора правильного предкомпилированных параметрах флагов (т. е native) образ, который будет загружена в этот процесс.</span><span class="sxs-lookup"><span data-stu-id="e7adc-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7adc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7adc-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7adc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7adc-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="e7adc-106">[out] Указатель на побитовое сочетание [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) значений перечисления, которые используются для выбора нужного предварительно скомпилированного образа загрузки.</span><span class="sxs-lookup"><span data-stu-id="e7adc-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7adc-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7adc-107">Remarks</span></span>  
 <span data-ttu-id="e7adc-108">Используйте [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) метод, чтобы задать флаги, которые среда CLR будет использовать для выбора нужного предварительно скомпилированного образа загрузки.</span><span class="sxs-lookup"><span data-stu-id="e7adc-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7adc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e7adc-109">Requirements</span></span>  
 <span data-ttu-id="e7adc-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7adc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7adc-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7adc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7adc-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7adc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7adc-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7adc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
