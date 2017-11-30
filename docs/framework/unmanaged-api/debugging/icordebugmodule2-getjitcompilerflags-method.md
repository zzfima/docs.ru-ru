---
title: "Метод ICorDebugModule2::GetJITCompilerFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.GetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0a158b779ad85b8161d6f6ea8bf2dc4c1db1a283
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="a2715-102">Метод ICorDebugModule2::GetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="a2715-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="a2715-103">Получает флаги, управляющие компиляции этого ICorDebugModule2 just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a2715-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2715-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2715-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2715-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2715-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="a2715-106">[out] Указатель на значение [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисления, который управляет JIT-компиляции.</span><span class="sxs-lookup"><span data-stu-id="a2715-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2715-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a2715-107">Requirements</span></span>  
 <span data-ttu-id="a2715-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2715-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2715-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a2715-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2715-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2715-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2715-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2715-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
