---
title: Метод ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
ms.openlocfilehash: 7f3010cccc584288608b3f6ba95efbeb95f271fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132062"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="c12c1-102">Метод ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="c12c1-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="c12c1-103">Возвращает значение Корелементтипе, которое описывает собственный тип <xref:System.Type> среды CLR, представленный этим объектом ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="c12c1-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c12c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c12c1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c12c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c12c1-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="c12c1-106">заполняет Указатель на значение перечисления `CorElementType`, указывающее <xref:System.Type> среды CLR, которую представляет этот `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="c12c1-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c12c1-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="c12c1-107">Remarks</span></span>  
 <span data-ttu-id="c12c1-108">Если значение `ty` — ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, то метод [ICorDebugType:: coclass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) можно вызвать, чтобы получить неэкземплярный тип для универсального типа. в противном случае не вызывайте `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="c12c1-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c12c1-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c12c1-109">Requirements</span></span>  
 <span data-ttu-id="c12c1-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c12c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c12c1-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c12c1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c12c1-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c12c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c12c1-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c12c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
