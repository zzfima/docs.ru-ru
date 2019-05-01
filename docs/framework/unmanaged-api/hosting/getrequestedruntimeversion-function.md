---
title: Функция GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ee737f4c6d34e77996f5ba08ce4d84132a99238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985664"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="13453-102">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="13453-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="13453-103">Возвращает номер версии общеязыковой среды выполнения (CLR), запрашиваемой указанным приложением.</span><span class="sxs-lookup"><span data-stu-id="13453-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="13453-104">Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрашиваемой.</span><span class="sxs-lookup"><span data-stu-id="13453-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="13453-105">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13453-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13453-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13453-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13453-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="13453-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="13453-108">[in] Имя приложения.</span><span class="sxs-lookup"><span data-stu-id="13453-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="13453-109">[out] Буфер, содержащий строку номера версии после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="13453-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="13453-110">[in] Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="13453-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="13453-111">[out] Указатель на длину строку номера версии.</span><span class="sxs-lookup"><span data-stu-id="13453-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13453-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="13453-112">Return Value</span></span>  
 <span data-ttu-id="13453-113">Этот метод возвращает стандартные коды ошибок объектов модели компонентов (COM), как определено в файле WinError.h, помимо следующих значений.</span><span class="sxs-lookup"><span data-stu-id="13453-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="13453-114">Код возврата</span><span class="sxs-lookup"><span data-stu-id="13453-114">Return code</span></span>|<span data-ttu-id="13453-115">Описание</span><span class="sxs-lookup"><span data-stu-id="13453-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="13453-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="13453-116">S_OK</span></span>|<span data-ttu-id="13453-117">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="13453-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="13453-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="13453-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="13453-119">Версии буфера недостаточен для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="13453-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="13453-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="13453-120">E_POINTER</span></span>|<span data-ttu-id="13453-121">Параметр `pdwLength` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="13453-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13453-122">Требования</span><span class="sxs-lookup"><span data-stu-id="13453-122">Requirements</span></span>  
 <span data-ttu-id="13453-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13453-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13453-124">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13453-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13453-125">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13453-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13453-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13453-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13453-127">См. также</span><span class="sxs-lookup"><span data-stu-id="13453-127">See also</span></span>

- [<span data-ttu-id="13453-128">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="13453-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="13453-129">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="13453-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="13453-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="13453-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
