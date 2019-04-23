---
title: Метод ICLRMetaHost::GetVersionFromFile
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a6c7fd48269a3e8291a548b3e13efe5c8e70652
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150817"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="d1130-102">Метод ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="d1130-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="d1130-103">Получает сборки .NET Framework компиляции оригинального (хранится в метаданных), по его пути файла.</span><span class="sxs-lookup"><span data-stu-id="d1130-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="d1130-104">Этот метод заменяет [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="d1130-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1130-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1130-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1130-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1130-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="d1130-107">[in] Путь к файлу завершения сборки.</span><span class="sxs-lookup"><span data-stu-id="d1130-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="d1130-108">[out] Версия .NET Framework компиляции, хранятся в метаданных, в формате «v*объект*. *B*[. *X*]».</span><span class="sxs-lookup"><span data-stu-id="d1130-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="d1130-109">*Объект*, *B*, и *X* — десятичные числа, соответствующие основной номер версии, дополнительный номер версии и номер сборки.</span><span class="sxs-lookup"><span data-stu-id="d1130-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="d1130-110">Длина этой строки ограничена MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="d1130-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1130-111">Эти выходные данные совпадает с именем каталога для версии .NET Framework, как оно отображается в разделе C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="d1130-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="d1130-112">Пример значения: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *X*«, где *X* зависит от номера установленного построения.</span><span class="sxs-lookup"><span data-stu-id="d1130-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="d1130-113">Обратите внимание, что префикс «v» является обязательным.</span><span class="sxs-lookup"><span data-stu-id="d1130-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="d1130-114">[in, out] Размер `pwzbuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="d1130-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1130-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d1130-115">Return Value</span></span>  
 <span data-ttu-id="d1130-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="d1130-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d1130-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d1130-117">HRESULT</span></span>|<span data-ttu-id="d1130-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d1130-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d1130-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d1130-119">S_OK</span></span>|<span data-ttu-id="d1130-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d1130-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="d1130-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d1130-121">E_POINTER</span></span>|<span data-ttu-id="d1130-122">`pwzbuffer` или `pcchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="d1130-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="d1130-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="d1130-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="d1130-124">Буфер слишком мал.</span><span class="sxs-lookup"><span data-stu-id="d1130-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d1130-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d1130-125">Requirements</span></span>  
 <span data-ttu-id="d1130-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1130-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1130-127">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d1130-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d1130-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1130-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1130-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1130-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1130-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d1130-130">See also</span></span>

- [<span data-ttu-id="d1130-131">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="d1130-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="d1130-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="d1130-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
