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
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178119"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="e2f6e-102">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="e2f6e-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="e2f6e-103">Получает номер версии общего времени выполнения языка (CLR), который связан с указанной ручкой процесса.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="e2f6e-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f6e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2f6e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2f6e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2f6e-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="e2f6e-107">(в) Ручка к процессу.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="e2f6e-108">(ваут) Буфер, содержащий строку числа версий после успешного завершения метода.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="e2f6e-109">(в) Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="e2f6e-110">(ваут) Указатель на длину строки номера версии.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2f6e-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2f6e-111">Return Value</span></span>  
 <span data-ttu-id="e2f6e-112">Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="e2f6e-113">Код возврата</span><span class="sxs-lookup"><span data-stu-id="e2f6e-113">Return code</span></span>|<span data-ttu-id="e2f6e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="e2f6e-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e2f6e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="e2f6e-115">S_OK</span></span>|<span data-ttu-id="e2f6e-116">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="e2f6e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e2f6e-117">E_INVALIDARG</span></span>|<span data-ttu-id="e2f6e-118">`pVersion`является недействительным `cchBuffer` и не является недействительным, или наоборот.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="e2f6e-119">-или-</span><span class="sxs-lookup"><span data-stu-id="e2f6e-119">-or-</span></span><br /><br /> <span data-ttu-id="e2f6e-120">`hProcess`не является допустимой ручкой для процесса.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="e2f6e-121">-или-</span><span class="sxs-lookup"><span data-stu-id="e2f6e-121">-or-</span></span><br /><br /> <span data-ttu-id="e2f6e-122">CLR не загружается.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="e2f6e-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e2f6e-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e2f6e-124">`cchBuffer`является нулевым или меньше, чем длина строки версии.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="e2f6e-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e2f6e-125">E_NOTIMPL</span></span>|<span data-ttu-id="e2f6e-126">Этот метод недоступен на операционной системе Microsoft Windows 95, Microsoft Windows 98 или Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="e2f6e-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e2f6e-127">Требования</span><span class="sxs-lookup"><span data-stu-id="e2f6e-127">Requirements</span></span>  
 <span data-ttu-id="e2f6e-128">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2f6e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2f6e-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2f6e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2f6e-130">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2f6e-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2f6e-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2f6e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f6e-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2f6e-132">See also</span></span>

- [<span data-ttu-id="e2f6e-133">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="e2f6e-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="e2f6e-134">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="e2f6e-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="e2f6e-135">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="e2f6e-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
