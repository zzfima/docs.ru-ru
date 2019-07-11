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
ms.openlocfilehash: 4015ecec38466650488a653641f5af93c4680f22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779594"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="06559-102">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="06559-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="06559-103">Получает номер версии общей языковой среды выполнения (CLR), связанный с указанным дескриптором процесса.</span><span class="sxs-lookup"><span data-stu-id="06559-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="06559-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="06559-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06559-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06559-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06559-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="06559-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="06559-107">[in] Дескриптор процесса.</span><span class="sxs-lookup"><span data-stu-id="06559-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="06559-108">[out] Буфер, содержащий строку номера версии после успешного завершения метода.</span><span class="sxs-lookup"><span data-stu-id="06559-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="06559-109">[in] Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="06559-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="06559-110">[out] Указатель на длину строку номера версии.</span><span class="sxs-lookup"><span data-stu-id="06559-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06559-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="06559-111">Return Value</span></span>  
 <span data-ttu-id="06559-112">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="06559-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="06559-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="06559-113">Return code</span></span>|<span data-ttu-id="06559-114">Описание</span><span class="sxs-lookup"><span data-stu-id="06559-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="06559-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="06559-115">S_OK</span></span>|<span data-ttu-id="06559-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="06559-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="06559-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="06559-117">E_INVALIDARG</span></span>|<span data-ttu-id="06559-118">`pVersion` имеет значение null и `cchBuffer` не равно null, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="06559-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="06559-119">-или-</span><span class="sxs-lookup"><span data-stu-id="06559-119">-or-</span></span><br /><br /> <span data-ttu-id="06559-120">`hProcess` не является допустимым дескриптором к процессу.</span><span class="sxs-lookup"><span data-stu-id="06559-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="06559-121">-или-</span><span class="sxs-lookup"><span data-stu-id="06559-121">-or-</span></span><br /><br /> <span data-ttu-id="06559-122">Среда CLR не загружается.</span><span class="sxs-lookup"><span data-stu-id="06559-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="06559-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="06559-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="06559-124">`cchBuffer` равно null или меньше, чем длина строки версии.</span><span class="sxs-lookup"><span data-stu-id="06559-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="06559-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="06559-125">E_NOTIMPL</span></span>|<span data-ttu-id="06559-126">Этот метод не доступен в операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="06559-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06559-127">Требования</span><span class="sxs-lookup"><span data-stu-id="06559-127">Requirements</span></span>  
 <span data-ttu-id="06559-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06559-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06559-129">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="06559-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06559-130">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="06559-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06559-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06559-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06559-132">См. также</span><span class="sxs-lookup"><span data-stu-id="06559-132">See also</span></span>

- [<span data-ttu-id="06559-133">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="06559-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="06559-134">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="06559-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="06559-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="06559-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
