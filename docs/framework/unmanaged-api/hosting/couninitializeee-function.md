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
ms.openlocfilehash: 7b3712b4cb66facc105a03d7bfad235f09339056
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193009"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="5d3dd-102">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="5d3dd-102">CoUninitializeEE Function</span></span>
`CoUninitializeEE` <span data-ttu-id="5d3dd-103">является устаревшим и не добавляет новых функций.</span><span class="sxs-lookup"><span data-stu-id="5d3dd-103">is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d3dd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d3dd-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="5d3dd-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d3dd-105">Remarks</span></span>  
 <span data-ttu-id="5d3dd-106">Ядро выполнения среды выполнения не может быть выгружена из процесса.</span><span class="sxs-lookup"><span data-stu-id="5d3dd-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="5d3dd-107">Чтобы завершить работу ядра выполнения следует вызвать [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="5d3dd-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3dd-108">См. также</span><span class="sxs-lookup"><span data-stu-id="5d3dd-108">See also</span></span>

- [<span data-ttu-id="5d3dd-109">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="5d3dd-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="5d3dd-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="5d3dd-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
