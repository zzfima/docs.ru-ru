---
title: Метод ICorDebugHandleValue::GetHandleType
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: bc7d99d0ddb443cba227b7bad0cd53edb94c9101
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138539"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="e49c7-102">Метод ICorDebugHandleValue::GetHandleType</span><span class="sxs-lookup"><span data-stu-id="e49c7-102">ICorDebugHandleValue::GetHandleType Method</span></span>
<span data-ttu-id="e49c7-103">Возвращает значение, указывающее тип маркера, на который ссылается этот объект ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="e49c7-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49c7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e49c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e49c7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e49c7-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="e49c7-106">заполняет Указатель на значение перечисления Кордебугхандлетипе, указывающее тип этого маркера.</span><span class="sxs-lookup"><span data-stu-id="e49c7-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49c7-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e49c7-107">Requirements</span></span>  
 <span data-ttu-id="e49c7-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e49c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e49c7-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e49c7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e49c7-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e49c7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e49c7-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e49c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
