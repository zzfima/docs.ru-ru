---
title: Функция NukeDownloadedCache
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80891da7d61aa5114d5cc4d8aff4c7ce82020237
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720097"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="c88fe-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="c88fe-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="c88fe-103">Удаляет кэше загрузки среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="c88fe-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c88fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c88fe-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c88fe-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c88fe-105">Return Value</span></span>  
 <span data-ttu-id="c88fe-106">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h.</span><span class="sxs-lookup"><span data-stu-id="c88fe-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c88fe-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="c88fe-107">Remarks</span></span>  
 <span data-ttu-id="c88fe-108">Кэш загрузки среды CLR — это область, где хранятся сборки со строгими именами, загруженным из URL-адрес для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="c88fe-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c88fe-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c88fe-109">Requirements</span></span>  
 <span data-ttu-id="c88fe-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c88fe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c88fe-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c88fe-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c88fe-112">**Библиотека:** Fusion.dll и "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="c88fe-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="c88fe-113">Используйте Fusion.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c88fe-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c88fe-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c88fe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88fe-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c88fe-115">See also</span></span>
- [<span data-ttu-id="c88fe-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="c88fe-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="c88fe-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="c88fe-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="c88fe-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="c88fe-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
