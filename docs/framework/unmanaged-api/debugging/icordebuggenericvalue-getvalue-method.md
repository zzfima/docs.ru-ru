---
title: Метод ICorDebugGenericValue::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53db4dcb13303c9e7bdd77a46b3c9526364bac06
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995649"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="ab139-102">Метод ICorDebugGenericValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="ab139-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="ab139-103">Значение этого универсального копируется в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="ab139-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab139-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab139-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab139-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab139-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="ab139-106">[out] Указатель на значение, представленное этим объектом ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="ab139-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="ab139-107">Значение может быть простым типом или ссылочным типом (то есть указатель).</span><span class="sxs-lookup"><span data-stu-id="ab139-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab139-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ab139-108">Requirements</span></span>  
 <span data-ttu-id="ab139-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab139-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab139-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab139-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab139-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab139-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab139-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab139-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
