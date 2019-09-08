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
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796308"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="19b7d-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="19b7d-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="19b7d-103">Удаляет кэш загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="19b7d-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="19b7d-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="19b7d-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="19b7d-105">Return Value</span></span>  
 <span data-ttu-id="19b7d-106">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h.</span><span class="sxs-lookup"><span data-stu-id="19b7d-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19b7d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="19b7d-107">Remarks</span></span>  
 <span data-ttu-id="19b7d-108">Кэш загрузки среды CLR — это область, в которой хранятся сборки со строгими именами, загружаемые из URL-адреса для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="19b7d-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19b7d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="19b7d-109">Requirements</span></span>  
 <span data-ttu-id="19b7d-110">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19b7d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19b7d-111">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="19b7d-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="19b7d-112">**Библиотечная** Fusion. dll и mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="19b7d-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="19b7d-113">Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19b7d-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="19b7d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19b7d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b7d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="19b7d-115">See also</span></span>

- [<span data-ttu-id="19b7d-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="19b7d-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="19b7d-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="19b7d-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="19b7d-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="19b7d-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
