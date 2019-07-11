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
ms.openlocfilehash: b17b36f66a9b8b78b16057ec37d3ee5f484f7ae2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779753"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="5b16b-102">Метод ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="5b16b-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="5b16b-103">Получает сборки .NET Framework компиляции оригинального (хранится в метаданных), по его пути файла.</span><span class="sxs-lookup"><span data-stu-id="5b16b-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="5b16b-104">Этот метод заменяет [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="5b16b-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b16b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b16b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b16b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b16b-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="5b16b-107">[in] Путь к файлу завершения сборки.</span><span class="sxs-lookup"><span data-stu-id="5b16b-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="5b16b-108">[out] Версия .NET Framework компиляции, хранятся в метаданных, в формате «v*объект*. *B*[. *X*]».</span><span class="sxs-lookup"><span data-stu-id="5b16b-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="5b16b-109">*Объект*, *B*, и *X* — десятичные числа, соответствующие основной номер версии, дополнительный номер версии и номер сборки.</span><span class="sxs-lookup"><span data-stu-id="5b16b-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="5b16b-110">Длина этой строки ограничена MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="5b16b-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b16b-111">Эти выходные данные совпадает с именем каталога для версии .NET Framework, как оно отображается в разделе C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="5b16b-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="5b16b-112">Пример значения: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *X*«, где *X* зависит от номера установленного построения.</span><span class="sxs-lookup"><span data-stu-id="5b16b-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="5b16b-113">Обратите внимание, что префикс «v» является обязательным.</span><span class="sxs-lookup"><span data-stu-id="5b16b-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="5b16b-114">[in, out] Размер `pwzbuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="5b16b-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b16b-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b16b-115">Return Value</span></span>  
 <span data-ttu-id="5b16b-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="5b16b-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5b16b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b16b-117">HRESULT</span></span>|<span data-ttu-id="5b16b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5b16b-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b16b-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b16b-119">S_OK</span></span>|<span data-ttu-id="5b16b-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="5b16b-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="5b16b-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5b16b-121">E_POINTER</span></span>|<span data-ttu-id="5b16b-122">`pwzbuffer` или `pcchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="5b16b-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="5b16b-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="5b16b-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="5b16b-124">Буфер слишком мал.</span><span class="sxs-lookup"><span data-stu-id="5b16b-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b16b-125">Требования</span><span class="sxs-lookup"><span data-stu-id="5b16b-125">Requirements</span></span>  
 <span data-ttu-id="5b16b-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b16b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b16b-127">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5b16b-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b16b-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b16b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b16b-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b16b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b16b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="5b16b-130">See also</span></span>

- [<span data-ttu-id="5b16b-131">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="5b16b-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="5b16b-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="5b16b-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
