---
title: Функция CoInitializeCor
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: e8d65e739504e01a7d11b37d1b34d7313b13a5e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138336"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="f571a-102">Функция CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="f571a-102">CoInitializeCor Function</span></span>
<span data-ttu-id="f571a-103">`CoInitializeCor` устарел.</span><span class="sxs-lookup"><span data-stu-id="f571a-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f571a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f571a-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="f571a-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="f571a-105">Remarks</span></span>  
 <span data-ttu-id="f571a-106">Чтобы инициализировать среду CLR, используйте либо [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) , либо [корбиндтокуррентрунтиме](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="f571a-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f571a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f571a-107">Requirements</span></span>  
 <span data-ttu-id="f571a-108">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f571a-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f571a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="f571a-109">See also</span></span>

- [<span data-ttu-id="f571a-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="f571a-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
