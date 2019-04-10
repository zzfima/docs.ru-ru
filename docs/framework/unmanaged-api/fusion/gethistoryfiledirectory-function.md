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
ms.openlocfilehash: b60dde31707175a27d2dc6c50484d6089adaeaa6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229632"
---
# <a name="gethistoryfiledirectory-function"></a><span data-ttu-id="d8789-102">Функция GetHistoryFileDirectory</span><span class="sxs-lookup"><span data-stu-id="d8789-102">GetHistoryFileDirectory Function</span></span>
<span data-ttu-id="d8789-103">Извлекает путь к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="d8789-103">Retrieves the path of the application history directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8789-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8789-104">Syntax</span></span>  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8789-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8789-105">Parameters</span></span>  
 `wzDir`  
 <span data-ttu-id="d8789-106">[out] Буфер для хранения пути к каталогу журнала приложения.</span><span class="sxs-lookup"><span data-stu-id="d8789-106">[out] A buffer to hold the path to the application history directory.</span></span>  
  
 `pdwSize`  
 <span data-ttu-id="d8789-107">[in, out] Длина буфера.</span><span class="sxs-lookup"><span data-stu-id="d8789-107">[in, out] The length of the buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8789-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d8789-108">Return Value</span></span>  
 <span data-ttu-id="d8789-109">Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError.h, а также следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d8789-109">This method returns standard COM error codes, as defined in the WinError.h file in addition to the following values.</span></span>  
  
|<span data-ttu-id="d8789-110">Код возврата</span><span class="sxs-lookup"><span data-stu-id="d8789-110">Return code</span></span>|<span data-ttu-id="d8789-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d8789-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d8789-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8789-112">S_OK</span></span>|<span data-ttu-id="d8789-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d8789-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="d8789-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d8789-114">E_INVALIDARG</span></span>|`wzDir` <span data-ttu-id="d8789-115">или `pdwSize` имеет значение null, или версии Неверная строка.</span><span class="sxs-lookup"><span data-stu-id="d8789-115">or `pdwSize` is null, or the version string is incorrect.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8789-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="d8789-116">Remarks</span></span>  
 <span data-ttu-id="d8789-117">При успешном завершении `pdwSize` аргумент имеет значение длины строки пути.</span><span class="sxs-lookup"><span data-stu-id="d8789-117">On successful completion, the `pdwSize` argument is set to the length of the path string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8789-118">Требования</span><span class="sxs-lookup"><span data-stu-id="d8789-118">Requirements</span></span>  
 <span data-ttu-id="d8789-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8789-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8789-120">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d8789-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d8789-121">**Библиотека:** Fusion.dll и "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="d8789-121">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="d8789-122">Используйте Fusion.dll вместо "Mscorwks.dll", чтобы обеспечить целевых правильную версию платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8789-122">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="d8789-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d8789-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8789-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d8789-124">See also</span></span>

- [<span data-ttu-id="d8789-125">Функция CreateHistoryReader</span><span class="sxs-lookup"><span data-stu-id="d8789-125">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)
- [<span data-ttu-id="d8789-126">Функция NukeDownloadedCache</span><span class="sxs-lookup"><span data-stu-id="d8789-126">NukeDownloadedCache Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)
- [<span data-ttu-id="d8789-127">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="d8789-127">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
