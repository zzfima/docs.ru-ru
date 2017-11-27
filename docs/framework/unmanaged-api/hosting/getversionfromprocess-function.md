---
title: "Функция GetVersionFromProcess"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetVersionFromProcess
helpviewer_keywords: GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c73d12731a5c72b8c0e724f74ee0aa9ebddeee9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="639fa-102">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="639fa-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="639fa-103">Получает номер версии среды common language runtime (CLR), связанный с заданным дескриптором процесса.</span><span class="sxs-lookup"><span data-stu-id="639fa-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="639fa-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="639fa-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639fa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="639fa-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="639fa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="639fa-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="639fa-107">[in] Дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="639fa-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="639fa-108">[out] Буфер, содержащий строку номера версии при успешном выполнении метода.</span><span class="sxs-lookup"><span data-stu-id="639fa-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="639fa-109">[in] Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="639fa-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="639fa-110">[out] Указатель на длину строку номера версии.</span><span class="sxs-lookup"><span data-stu-id="639fa-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="639fa-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="639fa-111">Return Value</span></span>  
 <span data-ttu-id="639fa-112">Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="639fa-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="639fa-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="639fa-113">Return code</span></span>|<span data-ttu-id="639fa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="639fa-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="639fa-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="639fa-115">S_OK</span></span>|<span data-ttu-id="639fa-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="639fa-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="639fa-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="639fa-117">E_INVALIDARG</span></span>|<span data-ttu-id="639fa-118">`pVersion`имеет значение null и `cchBuffer` не равно null, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="639fa-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="639fa-119">-или-</span><span class="sxs-lookup"><span data-stu-id="639fa-119">-or-</span></span><br /><br /> <span data-ttu-id="639fa-120">`hProcess`не является допустимым дескриптором для обработки.</span><span class="sxs-lookup"><span data-stu-id="639fa-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="639fa-121">-или-</span><span class="sxs-lookup"><span data-stu-id="639fa-121">-or-</span></span><br /><br /> <span data-ttu-id="639fa-122">Среда CLR не загружена.</span><span class="sxs-lookup"><span data-stu-id="639fa-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="639fa-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="639fa-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="639fa-124">`cchBuffer`значение null или меньше, чем длина строки версии.</span><span class="sxs-lookup"><span data-stu-id="639fa-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="639fa-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="639fa-125">E_NOTIMPL</span></span>|<span data-ttu-id="639fa-126">Этот метод недоступен в операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="639fa-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="639fa-127">Требования</span><span class="sxs-lookup"><span data-stu-id="639fa-127">Requirements</span></span>  
 <span data-ttu-id="639fa-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639fa-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639fa-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="639fa-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="639fa-130">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="639fa-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="639fa-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639fa-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639fa-132">См. также</span><span class="sxs-lookup"><span data-stu-id="639fa-132">See Also</span></span>  
 [<span data-ttu-id="639fa-133">GetRequestedRuntimeInfo-функция</span><span class="sxs-lookup"><span data-stu-id="639fa-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="639fa-134">GetRequestedRuntimeVersion-функция</span><span class="sxs-lookup"><span data-stu-id="639fa-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="639fa-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="639fa-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
