---
title: "Функция NukeDownloadedCache"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: NukeDownloadedCache
helpviewer_keywords: NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5ff24cf46ab24fe94ab19cee04d9e32ed1a34b53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="b8b4a-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="b8b4a-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="b8b4a-103">Удаляет кэше загрузки среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="b8b4a-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b4a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8b4a-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b8b4a-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b8b4a-105">Return Value</span></span>  
 <span data-ttu-id="b8b4a-106">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h.</span><span class="sxs-lookup"><span data-stu-id="b8b4a-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8b4a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8b4a-107">Remarks</span></span>  
 <span data-ttu-id="b8b4a-108">Кэш загрузки среды CLR — это область, где хранятся сборки со строгими именами, загруженных из URL-адреса для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="b8b4a-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8b4a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b8b4a-109">Requirements</span></span>  
 <span data-ttu-id="b8b4a-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8b4a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8b4a-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b8b4a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b8b4a-112">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="b8b4a-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="b8b4a-113">Используйте Fusion.dll вместо Mscorwks.dll, чтобы целевая правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8b4a-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b8b4a-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8b4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b4a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b8b4a-115">See Also</span></span>  
 [<span data-ttu-id="b8b4a-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="b8b4a-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="b8b4a-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="b8b4a-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="b8b4a-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="b8b4a-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
