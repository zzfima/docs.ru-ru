---
title: "Метод ICorDebugFrameEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrameEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a2139661621d7ebe2bf20e96b400096393964b89
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="967a8-102">Метод ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="967a8-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="967a8-103">Возвращает заданное число экземпляров ICorDebugFrame, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="967a8-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="967a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="967a8-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="967a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="967a8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="967a8-106">[in] Количество `ICorDebugFrame` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="967a8-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="967a8-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="967a8-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="967a8-108">[out] Указатель на число `ICorDebugFrame` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="967a8-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="967a8-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="967a8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="967a8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="967a8-110">Requirements</span></span>  
 <span data-ttu-id="967a8-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="967a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="967a8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="967a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="967a8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="967a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="967a8-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="967a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
