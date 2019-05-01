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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6b36c524921a4fecf8bc5ddcbace62af6450b6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993906"
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="9bc48-102">Метод ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="9bc48-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="9bc48-103">Получает значение CorElementType, описывающее в собственный тип общеязыковой среды выполнения (CLR) <xref:System.Type> представленный ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="9bc48-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bc48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bc48-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bc48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bc48-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="9bc48-106">[out] Указатель на значение `CorElementType` перечисление, указывающее, среда CLR <xref:System.Type> этим `ICorDebugType` представляет.</span><span class="sxs-lookup"><span data-stu-id="9bc48-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9bc48-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9bc48-107">Remarks</span></span>  
 <span data-ttu-id="9bc48-108">Если значение `ty` ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) метод может вызываться для получения типа без экземпляров универсального типа; в противном случае не вызывайте `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="9bc48-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bc48-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9bc48-109">Requirements</span></span>  
 <span data-ttu-id="9bc48-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bc48-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bc48-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bc48-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bc48-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bc48-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bc48-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bc48-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
