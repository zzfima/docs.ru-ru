---
title: Метод ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 711c85b930617632d69497e4a9cf0a74360d27f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415111"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="e6caf-102">Метод ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e6caf-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="e6caf-103">Получает заданное число экземпляров «ICorDebugCode» из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="e6caf-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6caf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6caf-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e6caf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6caf-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e6caf-106">[in] Количество `ICorDebugCode` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e6caf-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="e6caf-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugCode` объекта.</span><span class="sxs-lookup"><span data-stu-id="e6caf-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e6caf-108">[out] Указатель на число `ICorDebugCode` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="e6caf-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="e6caf-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="e6caf-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6caf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e6caf-110">Requirements</span></span>  
 <span data-ttu-id="e6caf-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6caf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6caf-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6caf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6caf-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6caf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6caf-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6caf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6caf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e6caf-115">See Also</span></span>  
    
 
