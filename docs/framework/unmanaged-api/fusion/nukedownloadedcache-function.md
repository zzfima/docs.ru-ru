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
ms.openlocfilehash: 76ada8400573dd61c25e0dce3f49ce66b5fb30c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773803"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="e4979-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="e4979-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="e4979-103">Удаляет кэше загрузки среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="e4979-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4979-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4979-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e4979-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e4979-105">Return Value</span></span>  
 <span data-ttu-id="e4979-106">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h.</span><span class="sxs-lookup"><span data-stu-id="e4979-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4979-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4979-107">Remarks</span></span>  
 <span data-ttu-id="e4979-108">Кэш загрузки среды CLR — это область, где хранятся сборки со строгими именами, загруженным из URL-адрес для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="e4979-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4979-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e4979-109">Requirements</span></span>  
 <span data-ttu-id="e4979-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4979-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4979-111">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e4979-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e4979-112">**Библиотека:** Fusion.dll и "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="e4979-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="e4979-113">Используйте Fusion.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e4979-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="e4979-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4979-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4979-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e4979-115">See also</span></span>

- [<span data-ttu-id="e4979-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="e4979-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="e4979-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="e4979-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)
- [<span data-ttu-id="e4979-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="e4979-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
