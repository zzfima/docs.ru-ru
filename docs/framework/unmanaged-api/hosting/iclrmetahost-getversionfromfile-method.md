---
title: "Метод ICLRMetaHost::GetVersionFromFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90fcf5ca8306c4e91ff6b96bac36ad2639d81d5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="1b09b-102">Метод ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="1b09b-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="1b09b-103">Получает сборки исходной версии платформы .NET Framework компиляции (хранятся в метаданных), по его пути файла.</span><span class="sxs-lookup"><span data-stu-id="1b09b-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="1b09b-104">Этот метод заменяет [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="1b09b-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b09b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b09b-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b09b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b09b-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="1b09b-107">[in] Путь к файлу завершения сборки.</span><span class="sxs-lookup"><span data-stu-id="1b09b-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="1b09b-108">[out] Версии платформы .NET Framework компиляции, хранятся в метаданных в формате «v*A*. *B*[. *X*]».</span><span class="sxs-lookup"><span data-stu-id="1b09b-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="1b09b-109">*Объект*, *B*, и *X* — десятичные числа, соответствуют основной номер версии, дополнительный номер версии и номер сборки.</span><span class="sxs-lookup"><span data-stu-id="1b09b-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="1b09b-110">Длина этой строки ограничена MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="1b09b-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b09b-111">Этот выход совпадает имя каталога для версии платформы .NET Framework, она появится в разделе C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="1b09b-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="1b09b-112">Примеры значений: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *X*», где *X* зависит от номера установленного построения.</span><span class="sxs-lookup"><span data-stu-id="1b09b-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="1b09b-113">Обратите внимание, что префикс «v» является обязательным.</span><span class="sxs-lookup"><span data-stu-id="1b09b-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="1b09b-114">[in, out] Размер `pwzbuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="1b09b-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b09b-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1b09b-115">Return Value</span></span>  
 <span data-ttu-id="1b09b-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="1b09b-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1b09b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b09b-117">HRESULT</span></span>|<span data-ttu-id="1b09b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1b09b-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b09b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b09b-119">S_OK</span></span>|<span data-ttu-id="1b09b-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="1b09b-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="1b09b-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1b09b-121">E_POINTER</span></span>|<span data-ttu-id="1b09b-122">`pwzbuffer` или `pcchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="1b09b-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="1b09b-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="1b09b-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="1b09b-124">Размер буфера слишком мал.</span><span class="sxs-lookup"><span data-stu-id="1b09b-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b09b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="1b09b-125">Requirements</span></span>  
 <span data-ttu-id="1b09b-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b09b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b09b-127">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1b09b-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1b09b-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b09b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b09b-129">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b09b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b09b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1b09b-130">See Also</span></span>  
 [<span data-ttu-id="1b09b-131">ICLRMetaHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1b09b-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="1b09b-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="1b09b-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
