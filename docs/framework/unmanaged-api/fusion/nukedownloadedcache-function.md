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
ms.openlocfilehash: 8f97614412eb2d49b202e86bdabc727159deb5d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131689"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="a50fd-102">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="a50fd-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="a50fd-103">Удаляет кэш загрузки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a50fd-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50fd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a50fd-104">Syntax</span></span>  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a50fd-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a50fd-105">Return Value</span></span>  
 <span data-ttu-id="a50fd-106">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h.</span><span class="sxs-lookup"><span data-stu-id="a50fd-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a50fd-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="a50fd-107">Remarks</span></span>  
 <span data-ttu-id="a50fd-108">Кэш загрузки среды CLR — это область, в которой хранятся сборки со строгими именами, загружаемые из URL-адреса для возможного повторного использования.</span><span class="sxs-lookup"><span data-stu-id="a50fd-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a50fd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a50fd-109">Requirements</span></span>  
 <span data-ttu-id="a50fd-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a50fd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50fd-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a50fd-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a50fd-112">**Библиотека:** Fusion. dll и mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="a50fd-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="a50fd-113">Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a50fd-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a50fd-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50fd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a50fd-115">See also</span></span>

- [<span data-ttu-id="a50fd-116">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="a50fd-116">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="a50fd-117">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="a50fd-117">GetHistoryFileDirectory Function</span></span>](gethistoryfiledirectory-function.md)
- [<span data-ttu-id="a50fd-118">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="a50fd-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
