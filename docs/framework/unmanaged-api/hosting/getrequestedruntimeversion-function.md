---
title: "Функция GetRequestedRuntimeVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersion
helpviewer_keywords: GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13309a7362f468d3711176db2adc7a82e3b949d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="ce356-102">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="ce356-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="ce356-103">Возвращает номер версии общеязыковой среды выполнения (CLR), запрашиваемые указанного приложения.</span><span class="sxs-lookup"><span data-stu-id="ce356-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="ce356-104">Если эта версия не установлена, Получает самую последнюю версию, установленную перед запрошенной версии.</span><span class="sxs-lookup"><span data-stu-id="ce356-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="ce356-105">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce356-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce356-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce356-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce356-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ce356-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="ce356-108">[in] Имя приложения.</span><span class="sxs-lookup"><span data-stu-id="ce356-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="ce356-109">[out] Буфер, содержащий строку номера версии при успешном выполнении.</span><span class="sxs-lookup"><span data-stu-id="ce356-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ce356-110">[in] Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="ce356-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="ce356-111">[out] Указатель на длину строку номера версии.</span><span class="sxs-lookup"><span data-stu-id="ce356-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce356-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ce356-112">Return Value</span></span>  
 <span data-ttu-id="ce356-113">Этот метод возвращает стандартные коды ошибок модели объектов компонентов (COM), как определено в файле WinError.h, кроме следующих значений.</span><span class="sxs-lookup"><span data-stu-id="ce356-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ce356-114">Код возврата</span><span class="sxs-lookup"><span data-stu-id="ce356-114">Return code</span></span>|<span data-ttu-id="ce356-115">Описание:</span><span class="sxs-lookup"><span data-stu-id="ce356-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ce356-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce356-116">S_OK</span></span>|<span data-ttu-id="ce356-117">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="ce356-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="ce356-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ce356-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ce356-119">Размер буфера версии недостаточен для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="ce356-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="ce356-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ce356-120">E_POINTER</span></span>|<span data-ttu-id="ce356-121">Параметр `pdwLength` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="ce356-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce356-122">Требования</span><span class="sxs-lookup"><span data-stu-id="ce356-122">Requirements</span></span>  
 <span data-ttu-id="ce356-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce356-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce356-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce356-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce356-125">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce356-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce356-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce356-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce356-127">См. также</span><span class="sxs-lookup"><span data-stu-id="ce356-127">See Also</span></span>  
 [<span data-ttu-id="ce356-128">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="ce356-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="ce356-129">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="ce356-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [<span data-ttu-id="ce356-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ce356-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
