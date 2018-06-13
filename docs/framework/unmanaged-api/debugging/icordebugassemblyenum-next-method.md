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
ms.openlocfilehash: b94ae83f2fb5f71abb8cb3a5c96aac9e268fc5db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405292"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="7965c-102">Метод ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="7965c-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="7965c-103">Возвращает заданное число сборок из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="7965c-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7965c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7965c-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7965c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7965c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7965c-106">[in] Число сборок, которые требуется получить.</span><span class="sxs-lookup"><span data-stu-id="7965c-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="7965c-107">[out] Массив указателей, каждый из которых указывает на объект ICorDebugAssembly, представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="7965c-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="7965c-108">[out] Указатель на число сборок, фактически извлеченных.</span><span class="sxs-lookup"><span data-stu-id="7965c-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="7965c-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="7965c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7965c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7965c-110">Requirements</span></span>  
 <span data-ttu-id="7965c-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7965c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7965c-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7965c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7965c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7965c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7965c-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7965c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
