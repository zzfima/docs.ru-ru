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
ms.openlocfilehash: 4733d59eb14f736f1369de82a7e9c677a65c3f86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093648"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="920d1-102">Метод ICorDebugCode2::GetCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="920d1-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="920d1-103">Получает флаги, задающие условия, при которых этот объект кода был либо just-in-time (JIT) скомпилированы или созданы с помощью генератора образов в машинном коде (Ngen.exe).</span><span class="sxs-lookup"><span data-stu-id="920d1-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="920d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="920d1-104">Syntax</span></span>  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="920d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="920d1-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="920d1-106">[out] Указатель на значение [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) перечисление, указывающее поведение JIT-компилятора или генератора образов в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="920d1-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="920d1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="920d1-107">Requirements</span></span>  
 <span data-ttu-id="920d1-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="920d1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="920d1-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="920d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="920d1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="920d1-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="920d1-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="920d1-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="920d1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="920d1-112">See also</span></span>
