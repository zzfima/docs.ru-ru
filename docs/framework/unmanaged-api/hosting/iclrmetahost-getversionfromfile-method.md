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
ms.openlocfilehash: dd5d2e820bd1d733bb4ab968a89174124bc91357
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962941"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="80ef4-102">Метод ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="80ef4-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="80ef4-103">Возвращает исходную версию компиляции .NET Framework сборки (хранящейся в метаданных) по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="80ef4-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="80ef4-104">Этот метод заменяет функцию [жетфилеверсион](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="80ef4-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ef4-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80ef4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80ef4-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="80ef4-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="80ef4-107">окне Полный путь к файлу сборки.</span><span class="sxs-lookup"><span data-stu-id="80ef4-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="80ef4-108">заполняет Версия компиляции .NET Framework, хранящаяся в метаданных, в формате "v*A*. *Б* [. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="80ef4-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="80ef4-109">*A*, *B*и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки.</span><span class="sxs-lookup"><span data-stu-id="80ef4-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="80ef4-110">Длина этой строки ограничена MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="80ef4-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80ef4-111">Эти выходные данные соответствуют имени каталога для .NET Framework версии, как отображается в разделе К:\виндовс\микрософт.нет\фрамеворк.</span><span class="sxs-lookup"><span data-stu-id="80ef4-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="80ef4-112">Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *X*", где *X* зависит от установленного номера сборки.</span><span class="sxs-lookup"><span data-stu-id="80ef4-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="80ef4-113">Обратите внимание, что требуется префикс "v".</span><span class="sxs-lookup"><span data-stu-id="80ef4-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="80ef4-114">[вход, выход] Размер `pwzbuffer` во избежание переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="80ef4-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80ef4-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="80ef4-115">Return Value</span></span>  
 <span data-ttu-id="80ef4-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="80ef4-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="80ef4-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="80ef4-117">HRESULT</span></span>|<span data-ttu-id="80ef4-118">Описание</span><span class="sxs-lookup"><span data-stu-id="80ef4-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80ef4-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="80ef4-119">S_OK</span></span>|<span data-ttu-id="80ef4-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="80ef4-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="80ef4-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="80ef4-121">E_POINTER</span></span>|<span data-ttu-id="80ef4-122">`pwzbuffer` или `pcchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="80ef4-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="80ef4-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="80ef4-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="80ef4-124">Буфер слишком мал.</span><span class="sxs-lookup"><span data-stu-id="80ef4-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80ef4-125">Требования</span><span class="sxs-lookup"><span data-stu-id="80ef4-125">Requirements</span></span>  
 <span data-ttu-id="80ef4-126">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ef4-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ef4-127">**Заголовок.** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="80ef4-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="80ef4-128">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="80ef4-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80ef4-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80ef4-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ef4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="80ef4-130">See also</span></span>

- [<span data-ttu-id="80ef4-131">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="80ef4-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="80ef4-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="80ef4-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
