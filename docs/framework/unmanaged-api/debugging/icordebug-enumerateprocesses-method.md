---
title: "Метод ICorDebug::EnumerateProcesses"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.EnumerateProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e48bc47945bc6c77758eeaa8597ad0ce57b72689
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="4481a-102">Метод ICorDebug::EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="4481a-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="4481a-103">Получает перечислитель для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="4481a-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4481a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4481a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4481a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4481a-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="4481a-106">Указатель на адрес объекта ICorDebugProcessEnum, который является перечислителем для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="4481a-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4481a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4481a-107">Requirements</span></span>  
 <span data-ttu-id="4481a-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4481a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4481a-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4481a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4481a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4481a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4481a-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4481a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4481a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4481a-112">See Also</span></span>  
 [<span data-ttu-id="4481a-113">ICorDebug-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4481a-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
