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
ms.openlocfilehash: c2a176764332eed6affda704c8bfaf546ef70880
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788989"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="561c1-102">Метод ICorDebug::EnumerateProcesses</span><span class="sxs-lookup"><span data-stu-id="561c1-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="561c1-103">Возвращает перечислитель для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="561c1-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="561c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="561c1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="561c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="561c1-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="561c1-106">Указатель на адрес объекта Икордебугпроцессенум, который является перечислителем для отлаживаемых процессов.</span><span class="sxs-lookup"><span data-stu-id="561c1-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="561c1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="561c1-107">Requirements</span></span>  
 <span data-ttu-id="561c1-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="561c1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="561c1-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="561c1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="561c1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="561c1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="561c1-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="561c1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561c1-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="561c1-112">See also</span></span>

- [<span data-ttu-id="561c1-113">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="561c1-113">ICorDebug Interface</span></span>](icordebug-interface.md)
