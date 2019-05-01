---
title: Функция GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b4ac1a37c2b3506216499ed0c9f8194949b768
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985651"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="f4e43-102">Функция GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="f4e43-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="f4e43-103">Получает соответствующий информация среды CLR (CLR) версии для класса с указанным `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="f4e43-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="f4e43-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4e43-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4e43-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4e43-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4e43-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f4e43-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="f4e43-107">[in]  `CLSID` Компонента.</span><span class="sxs-lookup"><span data-stu-id="f4e43-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f4e43-108">[out]  Буфер, содержащий строку номера версии после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="f4e43-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f4e43-109">[in]  Размер в расширенные символы из `pVersion` буфера.</span><span class="sxs-lookup"><span data-stu-id="f4e43-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f4e43-110">[out] Длина в байтах, возвращенного буфера.</span><span class="sxs-lookup"><span data-stu-id="f4e43-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="f4e43-111">[in]  Одно из значений CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="f4e43-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="f4e43-112">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f4e43-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="f4e43-113">CLSID_RESOLUTION_DEFAULT: (0x0) указывает, что следует использовать взаимодействия по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f4e43-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="f4e43-114">CLSID_RESOLUTION_REGISTERED: (0x1) указывает, следует ли выполнять поиск реестра и должна ли применяться политика оболочек совместимости.</span><span class="sxs-lookup"><span data-stu-id="f4e43-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f4e43-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f4e43-115">Return Value</span></span>  
  
|<span data-ttu-id="f4e43-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f4e43-116">HRESULT</span></span>|<span data-ttu-id="f4e43-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f4e43-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f4e43-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f4e43-118">S_OK</span></span>|<span data-ttu-id="f4e43-119">Функция успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="f4e43-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="f4e43-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f4e43-120">E_INVALIDARG</span></span>|<span data-ttu-id="f4e43-121">Один из параметров имеет недопустимый тип или формат.</span><span class="sxs-lookup"><span data-stu-id="f4e43-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="f4e43-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f4e43-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f4e43-123">`pVersion` Буфера недостаточен для хранения всей строки версии.</span><span class="sxs-lookup"><span data-stu-id="f4e43-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="f4e43-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="f4e43-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="f4e43-125">Отсутствует класс зарегистрирован с указанным `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="f4e43-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="f4e43-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f4e43-126">E_POINTER</span></span>|<span data-ttu-id="f4e43-127">`dwLength` имеет значение null, или `cchBuffer` достаточно велик для хранения строки версии, но `pVersion` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="f4e43-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f4e43-128">Требования</span><span class="sxs-lookup"><span data-stu-id="f4e43-128">Requirements</span></span>  
 <span data-ttu-id="f4e43-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4e43-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4e43-130">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f4e43-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f4e43-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4e43-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4e43-132">См. также</span><span class="sxs-lookup"><span data-stu-id="f4e43-132">See also</span></span>

- [<span data-ttu-id="f4e43-133">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="f4e43-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
