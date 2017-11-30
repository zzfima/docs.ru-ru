---
title: "Метод ICorDebugType::GetType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20e2a1415d5dda9c4097d984af46942ebcf2365a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegettype-method"></a><span data-ttu-id="6dbd2-102">Метод ICorDebugType::GetType</span><span class="sxs-lookup"><span data-stu-id="6dbd2-102">ICorDebugType::GetType Method</span></span>
<span data-ttu-id="6dbd2-103">Возвращает значение CorElementType, которое описывает собственный тип общеязыковой среды выполнения (CLR) <xref:System.Type> представленный ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="6dbd2-103">Gets a CorElementType value that describes the native type of the common language runtime (CLR) <xref:System.Type> represented by this ICorDebugType.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dbd2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6dbd2-104">Syntax</span></span>  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6dbd2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6dbd2-105">Parameters</span></span>  
 `ty`  
 <span data-ttu-id="6dbd2-106">[out] Указатель на значение `CorElementType` перечисление, указывающее, среда CLR <xref:System.Type> этим `ICorDebugType` представляет.</span><span class="sxs-lookup"><span data-stu-id="6dbd2-106">[out] A pointer to a value of the `CorElementType` enumeration that indicates the CLR <xref:System.Type> that this `ICorDebugType` represents.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6dbd2-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6dbd2-107">Remarks</span></span>  
 <span data-ttu-id="6dbd2-108">Если значение `ty` ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) метод можно вызвать для получения типа без экземпляров универсального типа; в противном случае не следует вызывать `ICorDebugType::GetClass`.</span><span class="sxs-lookup"><span data-stu-id="6dbd2-108">If the value of `ty` is either ELEMENT_TYPE_CLASS or ELEMENT_TYPE_VALUETYPE, the [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) method may be called to get the uninstantiated type for a generic type; otherwise, do not call `ICorDebugType::GetClass`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6dbd2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6dbd2-109">Requirements</span></span>  
 <span data-ttu-id="6dbd2-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dbd2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dbd2-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6dbd2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6dbd2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6dbd2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6dbd2-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dbd2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
