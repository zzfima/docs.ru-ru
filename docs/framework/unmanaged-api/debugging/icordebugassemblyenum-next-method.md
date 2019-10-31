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
ms.openlocfilehash: 86fa44b609b4b89cfaa28f0bfa7bbdce6217623f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122858"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="d9a32-102">Метод ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="d9a32-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="d9a32-103">Возвращает указанное количество сборок из коллекции, начиная с текущего положения курсора.</span><span class="sxs-lookup"><span data-stu-id="d9a32-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9a32-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9a32-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9a32-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9a32-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d9a32-106">окне Число извлекаемых сборок.</span><span class="sxs-lookup"><span data-stu-id="d9a32-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="d9a32-107">заполняет Массив указателей, каждый из которых указывает на объект ICorDebugAssembly, представляющий сборку.</span><span class="sxs-lookup"><span data-stu-id="d9a32-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d9a32-108">заполняет Указатель на число фактически возвращенных сборок.</span><span class="sxs-lookup"><span data-stu-id="d9a32-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="d9a32-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="d9a32-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9a32-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d9a32-110">Requirements</span></span>  
 <span data-ttu-id="d9a32-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9a32-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9a32-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9a32-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9a32-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9a32-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9a32-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9a32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
