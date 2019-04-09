---
title: Метод ICLRRuntimeInfo::GetVersionString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6e320936430307dab066eecc835ac5c84bd22bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202330"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="8d05d-102">Метод ICLRRuntimeInfo::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="8d05d-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="8d05d-103">Получает информация среды CLR (CLR) версии связанный с данной [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="8d05d-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="8d05d-104">Этот метод замещает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="8d05d-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="8d05d-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="8d05d-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [<span data-ttu-id="8d05d-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="8d05d-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="8d05d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d05d-107">Syntax</span></span>  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d05d-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d05d-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="8d05d-109">[out] Версия .NET Framework компиляции в формате «v*объект*. *B*[. *X*]».</span><span class="sxs-lookup"><span data-stu-id="8d05d-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="8d05d-110">*Объект*, *B*, и *X* — десятичные числа, соответствующие основной номер версии, дополнительный номер версии и номер сборки.</span><span class="sxs-lookup"><span data-stu-id="8d05d-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="8d05d-111">*X* является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8d05d-111">*X* is optional.</span></span> <span data-ttu-id="8d05d-112">Если *X* является не существует, отсутствует конечная точка не.</span><span class="sxs-lookup"><span data-stu-id="8d05d-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d05d-113">Этот параметр должно соответствовать имени каталога для версии платформы .NET Framework, как оно отображается в разделе C:\Windows\Microsoft.NET\Framework.</span><span class="sxs-lookup"><span data-stu-id="8d05d-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="8d05d-114">Пример значения: «v1.0.3705», «v1.1.4322», «v2.0.50727» и «v4.0. *x*«, где *x* зависит от номера установленного построения.</span><span class="sxs-lookup"><span data-stu-id="8d05d-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="8d05d-115">Обратите внимание, что префикс «v» является обязательным.</span><span class="sxs-lookup"><span data-stu-id="8d05d-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="8d05d-116">[in, out] Указывает размер `pwzBuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="8d05d-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="8d05d-117">Если `pwzBuffer` — `null`, `pchBuffer` возвращает требуемый размер `pwzBuffer` чтобы разрешить предварительное выделение.</span><span class="sxs-lookup"><span data-stu-id="8d05d-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8d05d-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8d05d-118">Return Value</span></span>  
 <span data-ttu-id="8d05d-119">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8d05d-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8d05d-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8d05d-120">HRESULT</span></span>|<span data-ttu-id="8d05d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="8d05d-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8d05d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="8d05d-122">S_OK</span></span>|<span data-ttu-id="8d05d-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8d05d-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="8d05d-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8d05d-124">E_POINTER</span></span>|`pwzBuffer` <span data-ttu-id="8d05d-125">или `pchBuffer` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="8d05d-125">or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d05d-126">Требования</span><span class="sxs-lookup"><span data-stu-id="8d05d-126">Requirements</span></span>  
 <span data-ttu-id="8d05d-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d05d-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d05d-128">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8d05d-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8d05d-129">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d05d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8d05d-130">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8d05d-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8d05d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="8d05d-131">See also</span></span>

- [<span data-ttu-id="8d05d-132">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="8d05d-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8d05d-133">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8d05d-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8d05d-134">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="8d05d-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="8d05d-135">Размещение</span><span class="sxs-lookup"><span data-stu-id="8d05d-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
