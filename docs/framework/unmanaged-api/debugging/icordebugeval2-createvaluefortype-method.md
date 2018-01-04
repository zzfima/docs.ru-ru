---
title: "Метод ICorDebugEval2::CreateValueForType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CreateValueForType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18e7eb5fc30c27fd2c4865dc61e2f75dc9e96068
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2createvaluefortype-method"></a><span data-ttu-id="d7fe8-102">Метод ICorDebugEval2::CreateValueForType</span><span class="sxs-lookup"><span data-stu-id="d7fe8-102">ICorDebugEval2::CreateValueForType Method</span></span>
<span data-ttu-id="d7fe8-103">Возвращает указатель на новый ICorDebugValue заданного типа с начальным значением, равным нулю или null.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-103">Gets a pointer to a new ICorDebugValue of the specified type, with an initial value of zero or null.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7fe8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7fe8-104">Syntax</span></span>  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7fe8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7fe8-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="d7fe8-106">[in] Указатель на объект ICorDebugType, который представляет тип.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-106">[in] Pointer to an ICorDebugType object that represents the type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="d7fe8-107">[out] Указатель на адрес `ICorDebugValue` объект, представляющий значение.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-107">[out] Pointer to the address of an `ICorDebugValue` object that represents the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7fe8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7fe8-108">Remarks</span></span>  
 <span data-ttu-id="d7fe8-109">`CreateValueForType`обобщает [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) , позволяя указывать тип произвольный объект, включая составить типы например `List<int>`.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-109">`CreateValueForType` generalizes [ICorDebugEval::CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) by allowing you to specify an arbitrary object type, including constructed types such as `List<int>`.</span></span> <span data-ttu-id="d7fe8-110">Этот метод предназначен только для создания значения, который может быть передан на вычисление функции.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-110">The only purpose of this method is to generate a value that can be passed to a function evaluation.</span></span>  
  
 <span data-ttu-id="d7fe8-111">Тип должен быть классом или типом значения.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-111">The type must be a class or a value type.</span></span> <span data-ttu-id="d7fe8-112">Этот метод нельзя использовать для создания массива значений или строковых значений.</span><span class="sxs-lookup"><span data-stu-id="d7fe8-112">You cannot use this method to create array values or string values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7fe8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d7fe8-113">Requirements</span></span>  
 <span data-ttu-id="d7fe8-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7fe8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7fe8-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7fe8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7fe8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7fe8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7fe8-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7fe8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
