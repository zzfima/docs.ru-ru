---
title: Функция CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73fa281d28e9b5362ff386b55b07dd431f1915f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429186"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="69630-102">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="69630-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="69630-103">`CoUninitializeEE` является устаревшим и не добавляет новых функций.</span><span class="sxs-lookup"><span data-stu-id="69630-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69630-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69630-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="69630-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="69630-105">Remarks</span></span>  
 <span data-ttu-id="69630-106">Исполняющий механизм среды выполнения не может быть выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="69630-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="69630-107">Завершение работы ядра выполнения следует вызвать [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="69630-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69630-108">См. также</span><span class="sxs-lookup"><span data-stu-id="69630-108">See Also</span></span>  
 [<span data-ttu-id="69630-109">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="69630-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="69630-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="69630-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
