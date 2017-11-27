---
title: "Метод ICorDebugFunction::GetCurrentVersionNumber"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetCurrentVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetCurrentVersionNumber
helpviewer_keywords:
- GetCurrentVersionNumber method [.NET Framework debugging]
- ICorDebugFunction::GetCurrentVersionNumber method [.NET Framework debugging]
ms.assetid: c3af1575-cbe6-457a-bc08-c53460edcbc8
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b4e26be7e50f7746caeb793bef6d6dbcfed7eef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetcurrentversionnumber-method"></a><span data-ttu-id="02336-102">Метод ICorDebugFunction::GetCurrentVersionNumber</span><span class="sxs-lookup"><span data-stu-id="02336-102">ICorDebugFunction::GetCurrentVersionNumber Method</span></span>
<span data-ttu-id="02336-103">Получает номер версии последней правки, внесенными в функцию, представленный этим объектом ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="02336-103">Gets the version number of the latest edit made to the function represented by this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02336-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02336-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentVersionNumber (  
    [out] ULONG32 *pnCurrentVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02336-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02336-105">Parameters</span></span>  
 `pnCurrentVersion`  
 <span data-ttu-id="02336-106">[out] Указатель на целое значение, представляющее номер версии последней правки этой функции.</span><span class="sxs-lookup"><span data-stu-id="02336-106">[out] A pointer to an integer value that is the version number of the latest edit made to this function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02336-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="02336-107">Remarks</span></span>  
 <span data-ttu-id="02336-108">Номер версии последней правки этой функции может быть больше номера версии самой функции.</span><span class="sxs-lookup"><span data-stu-id="02336-108">The version number of the latest edit made to this function may be greater than the version number of the function itself.</span></span> <span data-ttu-id="02336-109">Используйте либо [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) метода или [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) метод, чтобы получить номер версии функции.</span><span class="sxs-lookup"><span data-stu-id="02336-109">Use either the [ICorDebugFunction2::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md) method or the [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method to retrieve the version number of the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02336-110">Требования</span><span class="sxs-lookup"><span data-stu-id="02336-110">Requirements</span></span>  
 <span data-ttu-id="02336-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02336-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02336-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02336-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02336-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02336-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02336-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02336-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
