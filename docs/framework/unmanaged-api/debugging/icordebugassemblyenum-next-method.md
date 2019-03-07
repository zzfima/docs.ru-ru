---
title: Метод ICorDebugAssemblyEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25861b2635605042acc1bf81f3f7a4739e678522
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493119"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="c183a-102">Метод ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c183a-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="c183a-103">Получает заданное число сборок из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="c183a-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c183a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c183a-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c183a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c183a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c183a-106">[in] Количество сборок, которые требуется извлечь.</span><span class="sxs-lookup"><span data-stu-id="c183a-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="c183a-107">[out] Массив указателей, каждый из которых указывает ICorDebugAssembly объект, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="c183a-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c183a-108">[out] Указатель на количество фактически возвращенных сборок.</span><span class="sxs-lookup"><span data-stu-id="c183a-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="c183a-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="c183a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c183a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c183a-110">Requirements</span></span>  
 <span data-ttu-id="c183a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c183a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c183a-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c183a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c183a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c183a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c183a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c183a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
