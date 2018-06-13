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
ms.openlocfilehash: 53d40c198b53370733009c76fd3d49f14df93e6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402100"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="a0280-102">Метод ICorDebug::EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="a0280-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="a0280-103">Получает перечислитель для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="a0280-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0280-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0280-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a0280-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0280-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="a0280-106">Указатель на адрес объекта ICorDebugProcessEnum, который является перечислителем для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="a0280-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0280-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a0280-107">Requirements</span></span>  
 <span data-ttu-id="a0280-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0280-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0280-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0280-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0280-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0280-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0280-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0280-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0280-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a0280-112">See Also</span></span>  
 [<span data-ttu-id="a0280-113">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="a0280-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
