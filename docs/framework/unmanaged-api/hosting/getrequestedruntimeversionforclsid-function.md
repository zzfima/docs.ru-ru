---
title: "Функция GetRequestedRuntimeVersionForCLSID"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="4980a-102">Функция GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="4980a-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="4980a-103">Получает соответствующий общий среды выполнения (CLR) сведения о языке для класса с указанным `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="4980a-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="4980a-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4980a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4980a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4980a-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4980a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4980a-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="4980a-107">[in]  `CLSID` Компонента.</span><span class="sxs-lookup"><span data-stu-id="4980a-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4980a-108">[out]  Буфер, содержащий строку номера версии при успешном выполнении.</span><span class="sxs-lookup"><span data-stu-id="4980a-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4980a-109">[in]  Размер в расширенные символы из `pVersion` буфера.</span><span class="sxs-lookup"><span data-stu-id="4980a-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="4980a-110">[out] Длина возвращаемого буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="4980a-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="4980a-111">[in]  Одно из значений CLSID_RESOLUTION_FLAGS.</span><span class="sxs-lookup"><span data-stu-id="4980a-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="4980a-112">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="4980a-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="4980a-113">CLSID_RESOLUTION_DEFAULT: (0x0) указывает взаимодействия поведение по умолчанию следует использовать.</span><span class="sxs-lookup"><span data-stu-id="4980a-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="4980a-114">CLSID_RESOLUTION_REGISTERED: (0x1) указывает, что реестр следует выполнять поиск и создать оболочку политики должны быть применены.</span><span class="sxs-lookup"><span data-stu-id="4980a-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4980a-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4980a-115">Return Value</span></span>  
  
|<span data-ttu-id="4980a-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4980a-116">HRESULT</span></span>|<span data-ttu-id="4980a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="4980a-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4980a-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="4980a-118">S_OK</span></span>|<span data-ttu-id="4980a-119">Функция успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="4980a-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="4980a-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4980a-120">E_INVALIDARG</span></span>|<span data-ttu-id="4980a-121">Один из параметров имеет недопустимый тип или формат.</span><span class="sxs-lookup"><span data-stu-id="4980a-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="4980a-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4980a-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4980a-123">`pVersion` Буфер недостаточно велик для хранения всю строку версии.</span><span class="sxs-lookup"><span data-stu-id="4980a-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="4980a-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="4980a-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="4980a-125">Нет зарегистрированных с помощью указанного класса `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="4980a-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="4980a-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4980a-126">E_POINTER</span></span>|<span data-ttu-id="4980a-127">`dwLength`имеет значение null, или `cchBuffer` достаточно велик для хранения строки версии, но `pVersion` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="4980a-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4980a-128">Требования</span><span class="sxs-lookup"><span data-stu-id="4980a-128">Requirements</span></span>  
 <span data-ttu-id="4980a-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4980a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4980a-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4980a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4980a-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4980a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4980a-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4980a-132">See Also</span></span>  
 [<span data-ttu-id="4980a-133">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="4980a-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
