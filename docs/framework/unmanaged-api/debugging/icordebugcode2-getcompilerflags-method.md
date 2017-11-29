---
title: "Метод ICorDebugCode2::GetCompilerFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2.GetCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42a4b8e54bd1ca7706be7e23653681430fb41a8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="65fc5-102">Метод ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="65fc5-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="65fc5-103">Получает флаги, задающие условия, при которых объект код был либо just-in-time (JIT) компилируется или созданы с помощью генератора образов в машинном коде (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="65fc5-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65fc5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65fc5-104">Syntax</span></span>  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65fc5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="65fc5-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="65fc5-106">[out] Указатель на значение [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисление, задающее поведение JIT-компилятора или генератора образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="65fc5-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65fc5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="65fc5-107">Requirements</span></span>  
 <span data-ttu-id="65fc5-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65fc5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65fc5-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65fc5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65fc5-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65fc5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65fc5-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65fc5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fc5-112">См. также</span><span class="sxs-lookup"><span data-stu-id="65fc5-112">See Also</span></span>  
 
