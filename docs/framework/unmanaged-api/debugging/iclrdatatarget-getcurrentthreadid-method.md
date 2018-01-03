---
title: "Метод ICLRDataTarget::GetCurrentThreadID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetCurrentThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fd2c39b20b823e18232081d1655a6770bafccc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="5d50f-102">Метод ICLRDataTarget::GetCurrentThreadID</span><span class="sxs-lookup"><span data-stu-id="5d50f-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="5d50f-103">Получает идентификатор операционной системы для текущего потока.</span><span class="sxs-lookup"><span data-stu-id="5d50f-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d50f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d50f-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d50f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d50f-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="5d50f-106">[out] Указатель на идентификатор операционной системы, текущего потока для целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="5d50f-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d50f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d50f-107">Remarks</span></span>  
 <span data-ttu-id="5d50f-108">Если нет текущего потока для целевого процесса `GetCurrentThreadID` может произойти сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5d50f-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d50f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5d50f-109">Requirements</span></span>  
 <span data-ttu-id="5d50f-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d50f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d50f-111">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5d50f-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5d50f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d50f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d50f-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d50f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d50f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5d50f-114">See Also</span></span>  
 [<span data-ttu-id="5d50f-115">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="5d50f-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
