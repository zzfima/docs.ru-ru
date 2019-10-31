---
title: Функция CoUninitializeCor
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: eddc2f29da0efd9e56df710203b1d7621ffc27a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136870"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="3c7da-102">Функция CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="3c7da-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="3c7da-103">`CoUninitializeCor` устарел.</span><span class="sxs-lookup"><span data-stu-id="3c7da-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c7da-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="3c7da-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="3c7da-105">Remarks</span></span>  
 <span data-ttu-id="3c7da-106">Среду CLR невозможно выгрузить из процесса.</span><span class="sxs-lookup"><span data-stu-id="3c7da-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="3c7da-107">Чтобы полностью удалить среду выполнения из выполняющегося процесса, необходимо завершить этот процесс.</span><span class="sxs-lookup"><span data-stu-id="3c7da-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7da-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3c7da-108">See also</span></span>

- [<span data-ttu-id="3c7da-109">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="3c7da-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
