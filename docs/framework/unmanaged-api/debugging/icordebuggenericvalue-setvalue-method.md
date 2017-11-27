---
title: "Метод ICorDebugGenericValue::SetValue"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue.SetValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue::SetValue
helpviewer_keywords:
- ICorDebugGenericValue::SetValue method [.NET Framework debugging]
- SetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: ed4c6458-0435-44fc-8e78-8ba00be362f2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f76bb1b017453d7ca890f9d6b1b603f9b0d790bc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvaluesetvalue-method"></a><span data-ttu-id="081ec-102">Метод ICorDebugGenericValue::SetValue</span><span class="sxs-lookup"><span data-stu-id="081ec-102">ICorDebugGenericValue::SetValue Method</span></span>
<span data-ttu-id="081ec-103">Копирует новое значение из указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="081ec-103">Copies a new value from the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="081ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="081ec-104">Syntax</span></span>  
  
```  
HRESULT SetValue (  
    [in] void      *pFrom  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="081ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="081ec-105">Parameters</span></span>  
 `pFrom`  
 <span data-ttu-id="081ec-106">[in] Указатель на буфер, из которого необходимо скопировать значение.</span><span class="sxs-lookup"><span data-stu-id="081ec-106">[in] A pointer to the buffer from which to copy the value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="081ec-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="081ec-107">Remarks</span></span>  
 <span data-ttu-id="081ec-108">Для ссылочных типов значение является ссылкой, не содержимое.</span><span class="sxs-lookup"><span data-stu-id="081ec-108">For reference types, the value is the reference, not the content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="081ec-109">Требования</span><span class="sxs-lookup"><span data-stu-id="081ec-109">Requirements</span></span>  
 <span data-ttu-id="081ec-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="081ec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="081ec-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="081ec-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="081ec-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="081ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="081ec-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="081ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
