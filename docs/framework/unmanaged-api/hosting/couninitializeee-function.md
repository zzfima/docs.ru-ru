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
ms.openlocfilehash: 3531cfc0815c3f8a9479e35b2df60b2825801b39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136849"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="0a58b-102">Функция CoUninitializeEE</span><span class="sxs-lookup"><span data-stu-id="0a58b-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="0a58b-103">`CoUninitializeEE` устарел и не предоставляет никаких функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="0a58b-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a58b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a58b-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="0a58b-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="0a58b-105">Remarks</span></span>  
 <span data-ttu-id="0a58b-106">Подсистема выполнения среды CLR не может быть выгружена из процесса.</span><span class="sxs-lookup"><span data-stu-id="0a58b-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="0a58b-107">Чтобы завершить работу подсистемы выполнения, [корекситпроцесс](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)вызов.</span><span class="sxs-lookup"><span data-stu-id="0a58b-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a58b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0a58b-108">See also</span></span>

- [<span data-ttu-id="0a58b-109">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="0a58b-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="0a58b-110">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="0a58b-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
