---
title: "Метод ICorDebugInternalFrame::GetFrameType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 476903ae8f1461a46d685bc3e549c3b6553d5c68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="0fb7d-102">Метод ICorDebugInternalFrame::GetFrameType</span><span class="sxs-lookup"><span data-stu-id="0fb7d-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="0fb7d-103">Получает тип данного внутреннего фрейма.</span><span class="sxs-lookup"><span data-stu-id="0fb7d-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0fb7d-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fb7d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0fb7d-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="0fb7d-106">[out] Указатель на значение перечисления CorDebugInternalFrameType, которое указывает тип внутреннего фрейма, представленный этим `ICorDebugInternalFrame` объекта.</span><span class="sxs-lookup"><span data-stu-id="0fb7d-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fb7d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="0fb7d-107">Remarks</span></span>  
 <span data-ttu-id="0fb7d-108">Тип внутреннего фрейма STUBFRAME_NONE никогда не будет.</span><span class="sxs-lookup"><span data-stu-id="0fb7d-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="0fb7d-109">Отладчики правильно учитывать типы нераспознанный внутреннего фрейма.</span><span class="sxs-lookup"><span data-stu-id="0fb7d-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fb7d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0fb7d-110">Requirements</span></span>  
 <span data-ttu-id="0fb7d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fb7d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fb7d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0fb7d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0fb7d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fb7d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fb7d-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fb7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
