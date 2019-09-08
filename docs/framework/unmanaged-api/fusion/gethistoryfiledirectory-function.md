---
title: Функция GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adbbf94dc36c6d82360ed532b283cd666a1a52ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796847"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="a63d2-102">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="a63d2-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="a63d2-103">Возвращает путь к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="a63d2-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a63d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a63d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a63d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a63d2-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="a63d2-106">заполняет Буфер для хранения пути к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="a63d2-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="a63d2-107">[вход, выход] Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="a63d2-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a63d2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a63d2-108">Return Value</span></span>  
 <span data-ttu-id="a63d2-109">Этот метод возвращает коды стандартных ошибок COM, как определено в файле WinError. h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="a63d2-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="a63d2-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="a63d2-110">Return code</span></span>|<span data-ttu-id="a63d2-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a63d2-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a63d2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a63d2-112">S_OK</span></span>|<span data-ttu-id="a63d2-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="a63d2-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="a63d2-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a63d2-114">E_INVALIDARG</span></span>|<span data-ttu-id="a63d2-115">`wzDir`или `pdwSize` имеет значение null, или строка версии неверна.</span><span class="sxs-lookup"><span data-stu-id="a63d2-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a63d2-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="a63d2-116">Remarks</span></span>  
 <span data-ttu-id="a63d2-117">При успешном завершении `pdwSize` аргументу присваивается длина строки пути.</span><span class="sxs-lookup"><span data-stu-id="a63d2-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a63d2-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a63d2-118">Requirements</span></span>  
 <span data-ttu-id="a63d2-119">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a63d2-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a63d2-120">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a63d2-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a63d2-121">**Библиотечная** Fusion. dll и mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="a63d2-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="a63d2-122">Используйте Fusion. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a63d2-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a63d2-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a63d2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63d2-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a63d2-124">See also</span></span>

- [<span data-ttu-id="a63d2-125">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="a63d2-125">CreateHistoryReader Function</span></span>](createhistoryreader-function.md)
- [<span data-ttu-id="a63d2-126">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="a63d2-126">NukeDownloadedCache Function</span></span>](nukedownloadedcache-function.md)
- [<span data-ttu-id="a63d2-127">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="a63d2-127">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
