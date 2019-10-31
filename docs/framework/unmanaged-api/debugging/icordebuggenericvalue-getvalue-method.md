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
ms.openlocfilehash: 7923008eecb9011bead685fbbb7f05f81f12329b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138577"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="9be50-102">Метод ICorDebugGenericValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="9be50-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="9be50-103">Копирует значение этого универсального объекта в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="9be50-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9be50-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9be50-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9be50-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="9be50-106">заполняет Указатель на значение, представленное этим объектом ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="9be50-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="9be50-107">Значение может быть простым типом или ссылочным типом (т. е. указателем).</span><span class="sxs-lookup"><span data-stu-id="9be50-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9be50-108">Требования</span><span class="sxs-lookup"><span data-stu-id="9be50-108">Requirements</span></span>  
 <span data-ttu-id="9be50-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9be50-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9be50-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9be50-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9be50-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9be50-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9be50-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9be50-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
