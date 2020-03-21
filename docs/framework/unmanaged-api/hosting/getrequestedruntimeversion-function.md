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
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178140"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="b57e1-102">Функция GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="b57e1-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="b57e1-103">Получает номер версии общего времени выполнения языка (CLR), запрошенный указанным приложением.</span><span class="sxs-lookup"><span data-stu-id="b57e1-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="b57e1-104">Если эта версия не установлена, получает самую последняя версия, которая установлена до запрашиваемых версий.</span><span class="sxs-lookup"><span data-stu-id="b57e1-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="b57e1-105">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="b57e1-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57e1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b57e1-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b57e1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b57e1-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="b57e1-108">(в) Название приложения.</span><span class="sxs-lookup"><span data-stu-id="b57e1-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="b57e1-109">(ваут) Буфер, содержащий строку номера версии после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="b57e1-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b57e1-110">(в) Длина буфера версии.</span><span class="sxs-lookup"><span data-stu-id="b57e1-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="b57e1-111">(ваут) Указатель на длину строки номера версии.</span><span class="sxs-lookup"><span data-stu-id="b57e1-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b57e1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b57e1-112">Return Value</span></span>  
 <span data-ttu-id="b57e1-113">Этот метод возвращает стандартные коды ошибок компонентной модели объектов (COM), как это определено в WinError.h, в дополнение к следующим значениям.</span><span class="sxs-lookup"><span data-stu-id="b57e1-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="b57e1-114">Код возврата</span><span class="sxs-lookup"><span data-stu-id="b57e1-114">Return code</span></span>|<span data-ttu-id="b57e1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b57e1-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b57e1-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="b57e1-116">S_OK</span></span>|<span data-ttu-id="b57e1-117">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="b57e1-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="b57e1-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="b57e1-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="b57e1-119">Буфер версии недостаточно велик для хранения строки версии.</span><span class="sxs-lookup"><span data-stu-id="b57e1-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="b57e1-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b57e1-120">E_POINTER</span></span>|<span data-ttu-id="b57e1-121">Параметр `pdwLength` имеет значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b57e1-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b57e1-122">Требования</span><span class="sxs-lookup"><span data-stu-id="b57e1-122">Requirements</span></span>  
 <span data-ttu-id="b57e1-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b57e1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b57e1-124">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b57e1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b57e1-125">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b57e1-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b57e1-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b57e1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57e1-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b57e1-127">See also</span></span>

- [<span data-ttu-id="b57e1-128">Функция GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="b57e1-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="b57e1-129">Функция GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="b57e1-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="b57e1-130">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b57e1-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
