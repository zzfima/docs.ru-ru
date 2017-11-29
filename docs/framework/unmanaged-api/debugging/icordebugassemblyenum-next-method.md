---
title: "Метод ICorDebugAssemblyEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssemblyEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a7430a420769a2d7952caf93af3b1412094483f3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="a886b-102">Метод ICorDebugAssemblyEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a886b-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="a886b-103">Возвращает заданное число сборок из коллекции, начиная с текущей позиции курсора.</span><span class="sxs-lookup"><span data-stu-id="a886b-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a886b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a886b-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a886b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a886b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a886b-106">[in] Число сборок, которые требуется получить.</span><span class="sxs-lookup"><span data-stu-id="a886b-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a886b-107">[out] Массив указателей, каждый из которых указывает на объект ICorDebugAssembly, представляет сборку.</span><span class="sxs-lookup"><span data-stu-id="a886b-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a886b-108">[out] Указатель на число сборок, фактически извлеченных.</span><span class="sxs-lookup"><span data-stu-id="a886b-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="a886b-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="a886b-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a886b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a886b-110">Requirements</span></span>  
 <span data-ttu-id="a886b-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a886b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a886b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a886b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a886b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a886b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a886b-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a886b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
