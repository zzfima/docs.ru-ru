---
title: Метод ICorDebug::EnumerateProcesses
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bc82c506cf7e223e672a62ca74b215cac870e50
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123848"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="40fff-102">Метод ICorDebug::EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="40fff-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="40fff-103">Получает перечислитель для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="40fff-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40fff-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40fff-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40fff-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="40fff-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="40fff-106">Указатель на адрес объекта ICorDebugProcessEnum, который является перечислителем для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="40fff-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40fff-107">Требования</span><span class="sxs-lookup"><span data-stu-id="40fff-107">Requirements</span></span>  
 <span data-ttu-id="40fff-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40fff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40fff-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40fff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40fff-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40fff-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="40fff-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="40fff-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="40fff-112">См. также</span><span class="sxs-lookup"><span data-stu-id="40fff-112">See also</span></span>

- [<span data-ttu-id="40fff-113">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="40fff-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
