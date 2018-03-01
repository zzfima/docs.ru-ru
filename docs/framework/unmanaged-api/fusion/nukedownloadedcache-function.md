---
title: "Функция NukeDownloadedCache"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 31d7ba7d5f4a9268ea1e04a4c9f09cd17ebfd5bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="dd089-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="dd089-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="dd089-103">Удаляет кэше загрузки среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="dd089-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd089-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd089-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dd089-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dd089-105">Return Value</span></span>  
 <span data-ttu-id="dd089-106">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h.</span><span class="sxs-lookup"><span data-stu-id="dd089-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd089-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd089-107">Remarks</span></span>  
 <span data-ttu-id="dd089-108">Кэш загрузки среды CLR — это область, где хранятся сборки со строгими именами, загруженных из URL-адреса для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="dd089-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd089-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dd089-109">Requirements</span></span>  
 <span data-ttu-id="dd089-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd089-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd089-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="dd089-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dd089-112">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="dd089-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="dd089-113">Используйте Fusion.dll вместо Mscorwks.dll, чтобы целевая правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dd089-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="dd089-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd089-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd089-115">См. также</span><span class="sxs-lookup"><span data-stu-id="dd089-115">See Also</span></span>  
 [<span data-ttu-id="dd089-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="dd089-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="dd089-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="dd089-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="dd089-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="dd089-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
