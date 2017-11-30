---
title: "Функция CoInitializeCor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoInitializeCor
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CoInitializeCor
helpviewer_keywords: CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 119a01a33faeedc49931f3e7cbb1685b26366d0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="coinitializecor-function"></a><span data-ttu-id="e7451-102">Функция CoInitializeCor</span><span class="sxs-lookup"><span data-stu-id="e7451-102">CoInitializeCor Function</span></span>
<span data-ttu-id="e7451-103">`CoInitializeCor` устарел.</span><span class="sxs-lookup"><span data-stu-id="e7451-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7451-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7451-104">Syntax</span></span>  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e7451-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7451-105">Remarks</span></span>  
 <span data-ttu-id="e7451-106">Чтобы инициализировать общеязыковая среда выполнения, используйте [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) или [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="e7451-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7451-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e7451-107">Requirements</span></span>  
 <span data-ttu-id="e7451-108">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7451-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7451-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e7451-109">See Also</span></span>  
 [<span data-ttu-id="e7451-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="e7451-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
