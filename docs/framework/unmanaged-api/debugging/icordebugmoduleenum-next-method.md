---
title: Метод ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7624a22e5d65ae94797779a0b8cfa70f226450ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418988"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="b5c1e-102">Метод ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="b5c1e-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="b5c1e-103">Возвращает число экземпляров «ICorDebugModule», заданных параметром `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="b5c1e-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c1e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5c1e-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5c1e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5c1e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="b5c1e-106">[in] Количество `ICorDebugModule` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b5c1e-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="b5c1e-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugModule` объекта.</span><span class="sxs-lookup"><span data-stu-id="b5c1e-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b5c1e-108">[out] Указатель на число `ICorDebugModule` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="b5c1e-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="b5c1e-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="b5c1e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5c1e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b5c1e-110">Requirements</span></span>  
 <span data-ttu-id="b5c1e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5c1e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5c1e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5c1e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5c1e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5c1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5c1e-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5c1e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c1e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b5c1e-115">See Also</span></span>  
 
