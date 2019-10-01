---
title: Метод ICorDebugCode2::GetCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1605ee92c8743606ff0e958f112a2d90af43e03a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700718"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="07b89-102">Метод ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="07b89-102">ICorDebugCode2::GetCompilerFlags Method</span></span>

<span data-ttu-id="07b89-103">Возвращает флаги, указывающие условия, при которых этот объект кода был либо JIT-скомпилирован, либо создан с помощью генератора образов в машинном коде (Ngen. exe).</span><span class="sxs-lookup"><span data-stu-id="07b89-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>

## <a name="syntax"></a><span data-ttu-id="07b89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07b89-104">Syntax</span></span>

```cpp
HRESULT GetCompilerFlags (
    [out] DWORD *pdwFlags
);
```

## <a name="parameters"></a><span data-ttu-id="07b89-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="07b89-105">Parameters</span></span>

 `pdwFlags`  
 <span data-ttu-id="07b89-106">заполняет Указатель на значение перечисления [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) , которое указывает поведение JIT-компилятора или генератора образов в машинном код.</span><span class="sxs-lookup"><span data-stu-id="07b89-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>

## <a name="requirements"></a><span data-ttu-id="07b89-107">Требования</span><span class="sxs-lookup"><span data-stu-id="07b89-107">Requirements</span></span>

 <span data-ttu-id="07b89-108">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07b89-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="07b89-109">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="07b89-109">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="07b89-110">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="07b89-110">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="07b89-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07b89-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
 
