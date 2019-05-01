---
title: Функция GetVersionFromProcess
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 452104939acf5de7bb151cba00d65fb6631c98d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985638"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="e8643-102">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="e8643-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="e8643-103">Получает номер версии общей языковой среды выполнения (CLR), связанный с указанным дескриптором процесса.</span><span class="sxs-lookup"><span data-stu-id="e8643-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="e8643-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8643-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8643-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8643-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8643-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8643-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="e8643-107">[in] Дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="e8643-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="e8643-108">[out] Буфер, содержащий строку номера версии после успешного завершения метода.</span><span class="sxs-lookup"><span data-stu-id="e8643-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e8643-109">[in] Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="e8643-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="e8643-110">[out] Указатель на длину строку номера версии.</span><span class="sxs-lookup"><span data-stu-id="e8643-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8643-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e8643-111">Return Value</span></span>  
 <span data-ttu-id="e8643-112">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="e8643-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="e8643-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="e8643-113">Return code</span></span>|<span data-ttu-id="e8643-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e8643-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e8643-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e8643-115">S_OK</span></span>|<span data-ttu-id="e8643-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e8643-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="e8643-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e8643-117">E_INVALIDARG</span></span>|<span data-ttu-id="e8643-118">`pVersion` имеет значение null и `cchBuffer` не равно null, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="e8643-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="e8643-119">-или-</span><span class="sxs-lookup"><span data-stu-id="e8643-119">-or-</span></span><br /><br /> <span data-ttu-id="e8643-120">`hProcess` не является допустимым дескриптором к процессу.</span><span class="sxs-lookup"><span data-stu-id="e8643-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="e8643-121">-или-</span><span class="sxs-lookup"><span data-stu-id="e8643-121">-or-</span></span><br /><br /> <span data-ttu-id="e8643-122">Среда CLR не загружается.</span><span class="sxs-lookup"><span data-stu-id="e8643-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="e8643-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e8643-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e8643-124">`cchBuffer` равно null или меньше, чем длина строки версии.</span><span class="sxs-lookup"><span data-stu-id="e8643-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="e8643-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e8643-125">E_NOTIMPL</span></span>|<span data-ttu-id="e8643-126">Этот метод не доступен в операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="e8643-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8643-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e8643-127">Requirements</span></span>  
 <span data-ttu-id="e8643-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8643-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8643-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8643-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8643-130">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8643-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8643-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8643-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8643-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e8643-132">See also</span></span>

- [<span data-ttu-id="e8643-133">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e8643-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="e8643-134">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="e8643-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="e8643-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e8643-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
