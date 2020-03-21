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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178115"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="d0b91-102">Функция GetRequestedRuntimeVersionForCLSID</span><span class="sxs-lookup"><span data-stu-id="d0b91-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="d0b91-103">Получает соответствующую информацию о времени выполнения общего языка (CLR) для класса с указанным `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="d0b91-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="d0b91-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="d0b91-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b91-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0b91-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0b91-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0b91-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="d0b91-107">(в)  Компонента. `CLSID`</span><span class="sxs-lookup"><span data-stu-id="d0b91-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="d0b91-108">(ваут)  Буфер, содержащий строку номера версии после успешного завершения.</span><span class="sxs-lookup"><span data-stu-id="d0b91-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d0b91-109">(в)  Размер буфера, `pVersion` в широком характере.</span><span class="sxs-lookup"><span data-stu-id="d0b91-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d0b91-110">(ваут) Длина, в байтах, возвращенного буфера.</span><span class="sxs-lookup"><span data-stu-id="d0b91-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="d0b91-111">(в)  Одно из CLSID_RESOLUTION_FLAGS значений.</span><span class="sxs-lookup"><span data-stu-id="d0b91-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="d0b91-112">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="d0b91-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="d0b91-113">CLSID_RESOLUTION_DEFAULT: (0x0) указывает на то, что поведение интерп по умолчанию должно быть использовано.</span><span class="sxs-lookup"><span data-stu-id="d0b91-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="d0b91-114">CLSID_RESOLUTION_REGISTERED: (0x1) Указывает на то, что реестр должен быть проведен поиск и политика оболья должна быть применена.</span><span class="sxs-lookup"><span data-stu-id="d0b91-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0b91-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d0b91-115">Return Value</span></span>  
  
|<span data-ttu-id="d0b91-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d0b91-116">HRESULT</span></span>|<span data-ttu-id="d0b91-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d0b91-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d0b91-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="d0b91-118">S_OK</span></span>|<span data-ttu-id="d0b91-119">Функция успешно возвращается.</span><span class="sxs-lookup"><span data-stu-id="d0b91-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="d0b91-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d0b91-120">E_INVALIDARG</span></span>|<span data-ttu-id="d0b91-121">Один из параметров имеет недействительный тип или формат.</span><span class="sxs-lookup"><span data-stu-id="d0b91-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="d0b91-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d0b91-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d0b91-123">Буфер `pVersion` недостаточно велик, чтобы удерживать всю строку версии.</span><span class="sxs-lookup"><span data-stu-id="d0b91-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="d0b91-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="d0b91-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="d0b91-125">Нет класса, зарегистрированного `CLSID`с указанным .</span><span class="sxs-lookup"><span data-stu-id="d0b91-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="d0b91-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d0b91-126">E_POINTER</span></span>|<span data-ttu-id="d0b91-127">`dwLength`является нулевым, или `cchBuffer` достаточно большим, чтобы `pVersion` держать строку версии, но является недействительным.</span><span class="sxs-lookup"><span data-stu-id="d0b91-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d0b91-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d0b91-128">Requirements</span></span>  
 <span data-ttu-id="d0b91-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0b91-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0b91-130">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0b91-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0b91-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0b91-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b91-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d0b91-132">See also</span></span>

- [<span data-ttu-id="d0b91-133">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d0b91-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
