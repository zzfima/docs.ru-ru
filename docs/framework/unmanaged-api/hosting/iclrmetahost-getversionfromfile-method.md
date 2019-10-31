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
ms.openlocfilehash: a237dff63015cda2cf2ca86a64bb4028ec9b6e2c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140928"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="d9eae-102">Метод ICLRMetaHost::GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="d9eae-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="d9eae-103">Возвращает исходную версию компиляции .NET Framework сборки (хранящейся в метаданных) по указанному пути к файлу.</span><span class="sxs-lookup"><span data-stu-id="d9eae-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="d9eae-104">Этот метод заменяет функцию [жетфилеверсион](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d9eae-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9eae-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9eae-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9eae-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d9eae-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="d9eae-107">окне Полный путь к файлу сборки.</span><span class="sxs-lookup"><span data-stu-id="d9eae-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="d9eae-108">заполняет Версия компиляции .NET Framework, хранящаяся в метаданных, в формате "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="d9eae-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="d9eae-109">*A*, *B*и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки.</span><span class="sxs-lookup"><span data-stu-id="d9eae-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="d9eae-110">Длина этой строки ограничена MAX_PATH.</span><span class="sxs-lookup"><span data-stu-id="d9eae-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9eae-111">Эти выходные данные соответствуют имени каталога для .NET Framework версии, как отображается в разделе К:\виндовс\микрософт.нет\фрамеворк.</span><span class="sxs-lookup"><span data-stu-id="d9eae-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="d9eae-112">Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *X*", где *X* зависит от установленного номера сборки.</span><span class="sxs-lookup"><span data-stu-id="d9eae-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="d9eae-113">Обратите внимание, что требуется префикс "v".</span><span class="sxs-lookup"><span data-stu-id="d9eae-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="d9eae-114">[вход, выход] Размер `pwzbuffer`, чтобы избежать переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="d9eae-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9eae-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d9eae-115">Return Value</span></span>  
 <span data-ttu-id="d9eae-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="d9eae-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d9eae-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9eae-117">HRESULT</span></span>|<span data-ttu-id="d9eae-118">Описание</span><span class="sxs-lookup"><span data-stu-id="d9eae-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9eae-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9eae-119">S_OK</span></span>|<span data-ttu-id="d9eae-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="d9eae-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="d9eae-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d9eae-121">E_POINTER</span></span>|<span data-ttu-id="d9eae-122">`pwzbuffer` или `pcchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="d9eae-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="d9eae-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="d9eae-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="d9eae-124">Буфер слишком мал.</span><span class="sxs-lookup"><span data-stu-id="d9eae-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9eae-125">Требования</span><span class="sxs-lookup"><span data-stu-id="d9eae-125">Requirements</span></span>  
 <span data-ttu-id="d9eae-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9eae-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9eae-127">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="d9eae-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d9eae-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9eae-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9eae-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9eae-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9eae-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d9eae-130">See also</span></span>

- [<span data-ttu-id="d9eae-131">Интерфейс ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="d9eae-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="d9eae-132">Размещение</span><span class="sxs-lookup"><span data-stu-id="d9eae-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
