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
ms.openlocfilehash: d64064c29d2a03578305f71a37e759907814727e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="couninitializeee-function"></a><span data-ttu-id="79e93-102">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="79e93-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="79e93-103">`CoUninitializeEE`является устаревшим и не добавляет новых функций.</span><span class="sxs-lookup"><span data-stu-id="79e93-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79e93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79e93-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="79e93-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="79e93-105">Remarks</span></span>  
 <span data-ttu-id="79e93-106">Исполняющий механизм среды выполнения не может быть выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="79e93-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="79e93-107">Завершение работы ядра выполнения следует вызвать [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="79e93-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79e93-108">См. также</span><span class="sxs-lookup"><span data-stu-id="79e93-108">See Also</span></span>  
 [<span data-ttu-id="79e93-109">Coinitializeee-функция</span><span class="sxs-lookup"><span data-stu-id="79e93-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="79e93-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="79e93-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
