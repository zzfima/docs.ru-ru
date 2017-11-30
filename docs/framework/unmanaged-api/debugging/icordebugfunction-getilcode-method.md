---
title: "Метод ICorDebugFunction::GetILCode"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetILCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: da955f6eb8e7480fb23192e1a77341166dd40f3b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="c7fa0-102">Метод ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="c7fa0-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="c7fa0-103">Получает экземпляр ICorDebugCode, представляющее код Microsoft промежуточного языка MSIL, связанный с данным объектом ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="c7fa0-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7fa0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7fa0-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7fa0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7fa0-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="c7fa0-106">[out] Указатель на `ICorDebugCode` экземпляра, или значение null, если функция не была скомпилирована в MSIL.</span><span class="sxs-lookup"><span data-stu-id="c7fa0-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7fa0-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c7fa0-107">Remarks</span></span>  
 <span data-ttu-id="c7fa0-108">Если изменить и продолжить была разрешена в этой функции `GetILCode` метод получит код MSIL для этой функции измененной версии кода в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="c7fa0-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7fa0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c7fa0-109">Requirements</span></span>  
 <span data-ttu-id="c7fa0-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7fa0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7fa0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7fa0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7fa0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7fa0-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7fa0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
