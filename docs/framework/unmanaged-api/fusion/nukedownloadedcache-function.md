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
ms.openlocfilehash: f0436991512713c05e60a3c10d6fbdaa17bb378c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="6d273-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="6d273-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="6d273-103">Удаляет кэше загрузки среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="6d273-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d273-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d273-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="6d273-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6d273-105">Return Value</span></span>  
 <span data-ttu-id="6d273-106">Этот метод возвращает стандартные коды ошибок COM, определенные в файле WinError.h.</span><span class="sxs-lookup"><span data-stu-id="6d273-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d273-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d273-107">Remarks</span></span>  
 <span data-ttu-id="6d273-108">Кэш загрузки среды CLR — это область, где хранятся сборки со строгими именами, загруженных из URL-адреса для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="6d273-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d273-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6d273-109">Requirements</span></span>  
 <span data-ttu-id="6d273-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d273-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d273-111">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="6d273-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6d273-112">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="6d273-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="6d273-113">Используйте Fusion.dll вместо Mscorwks.dll, чтобы целевая правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d273-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="6d273-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d273-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d273-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6d273-115">See Also</span></span>  
 [<span data-ttu-id="6d273-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="6d273-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="6d273-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="6d273-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="6d273-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="6d273-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
