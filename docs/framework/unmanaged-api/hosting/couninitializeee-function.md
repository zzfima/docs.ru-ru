---
title: Функция CoUninitializeEE
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
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
ms.openlocfilehash: 2c4e22c2e80af37177294d86c2e5775a5c296fe7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211862"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="44645-102">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="44645-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="44645-103">`CoUninitializeEE` является устаревшим и не добавляет новых функций.</span><span class="sxs-lookup"><span data-stu-id="44645-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44645-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44645-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="44645-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="44645-105">Remarks</span></span>  
 <span data-ttu-id="44645-106">Ядро выполнения среды выполнения не может быть выгружена из процесса.</span><span class="sxs-lookup"><span data-stu-id="44645-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="44645-107">Чтобы завершить работу ядра выполнения следует вызвать [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="44645-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44645-108">См. также</span><span class="sxs-lookup"><span data-stu-id="44645-108">See also</span></span>
- [<span data-ttu-id="44645-109">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="44645-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="44645-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="44645-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
