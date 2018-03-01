---
title: "Функция GetHistoryFileDirectory"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5d0ec18a4f95d0d280a66b3b9d9200c560f5f187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="f5c90-102">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="f5c90-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="f5c90-103">Возвращает путь к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="f5c90-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c90-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5c90-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5c90-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5c90-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="f5c90-106">[out] Буфер для хранения пути к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="f5c90-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="f5c90-107">[in, out] Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="f5c90-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5c90-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f5c90-108">Return Value</span></span>  
 <span data-ttu-id="f5c90-109">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="f5c90-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="f5c90-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="f5c90-110">Return code</span></span>|<span data-ttu-id="f5c90-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="f5c90-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f5c90-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f5c90-112">S_OK</span></span>|<span data-ttu-id="f5c90-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="f5c90-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="f5c90-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f5c90-114">E_INVALIDARG</span></span>|<span data-ttu-id="f5c90-115">`wzDir`или `pdwSize` имеет значение null или версия Неверная строка.</span><span class="sxs-lookup"><span data-stu-id="f5c90-115">`wzDir` or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5c90-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="f5c90-116">Remarks</span></span>  
 <span data-ttu-id="f5c90-117">При успешном завершении `pdwSize` аргумент имеет значение длины строки пути.</span><span class="sxs-lookup"><span data-stu-id="f5c90-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5c90-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f5c90-118">Requirements</span></span>  
 <span data-ttu-id="f5c90-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5c90-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5c90-120">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f5c90-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f5c90-121">**Библиотека:** Fusion.dll и Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="f5c90-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="f5c90-122">Используйте Fusion.dll вместо Mscorwks.dll, чтобы целевая правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f5c90-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="f5c90-123">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5c90-123">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c90-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f5c90-124">See Also</span></span>  
 [<span data-ttu-id="f5c90-125">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="f5c90-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="f5c90-126">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="f5c90-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [<span data-ttu-id="f5c90-127">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="f5c90-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
