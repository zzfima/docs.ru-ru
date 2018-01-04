---
title: "Функция CoUninitializeEE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoUninitializeEE
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoUninitializeEE
helpviewer_keywords: CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4125a76ae50a293e35e326f775500c06120420d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="couninitializeee-function"></a><span data-ttu-id="bcc0d-102">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="bcc0d-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="bcc0d-103">`CoUninitializeEE`является устаревшим и не добавляет новых функций.</span><span class="sxs-lookup"><span data-stu-id="bcc0d-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcc0d-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="bcc0d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcc0d-105">Remarks</span></span>  
 <span data-ttu-id="bcc0d-106">Исполняющий механизм среды выполнения не может быть выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="bcc0d-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="bcc0d-107">Завершение работы ядра выполнения следует вызвать [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="bcc0d-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc0d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="bcc0d-108">See Also</span></span>  
 [<span data-ttu-id="bcc0d-109">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="bcc0d-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="bcc0d-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="bcc0d-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
