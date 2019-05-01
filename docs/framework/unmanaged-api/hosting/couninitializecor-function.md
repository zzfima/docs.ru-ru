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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0845c4d493cb3c750931a0ae2ad92b628a255c0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985755"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="cd5af-102">Функция CoUninitializeCor</span><span class="sxs-lookup"><span data-stu-id="cd5af-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="cd5af-103">`CoUninitializeCor` устарел.</span><span class="sxs-lookup"><span data-stu-id="cd5af-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd5af-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd5af-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="cd5af-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="cd5af-105">Remarks</span></span>  
 <span data-ttu-id="cd5af-106">Среда CLR не может быть выгружена из процесса.</span><span class="sxs-lookup"><span data-stu-id="cd5af-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="cd5af-107">Чтобы полностью удалить среду выполнения из запущенного процесса, необходимо завершить работу этого процесса.</span><span class="sxs-lookup"><span data-stu-id="cd5af-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd5af-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cd5af-108">See also</span></span>

- [<span data-ttu-id="cd5af-109">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="cd5af-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
