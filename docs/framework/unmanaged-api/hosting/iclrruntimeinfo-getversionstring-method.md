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
ms.openlocfilehash: 0b6ac83cdd0c88e87fdfd552c76c906a334f8928
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120299"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="0bf57-102">Метод ICLRRuntimeInfo::GetVersionString</span><span class="sxs-lookup"><span data-stu-id="0bf57-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="0bf57-103">Возвращает сведения о версии среды CLR, связанные с заданным интерфейсом [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0bf57-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="0bf57-104">Этот метод заменяет следующие функции:</span><span class="sxs-lookup"><span data-stu-id="0bf57-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="0bf57-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="0bf57-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="0bf57-106">жетрекуестедрунтимеверсион</span><span class="sxs-lookup"><span data-stu-id="0bf57-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="0bf57-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bf57-107">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bf57-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="0bf57-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="0bf57-109">заполняет Версия компиляции .NET Framework в формате "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="0bf57-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="0bf57-110">*A*, *B*и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки.</span><span class="sxs-lookup"><span data-stu-id="0bf57-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="0bf57-111">*X* является необязательным.</span><span class="sxs-lookup"><span data-stu-id="0bf57-111">*X* is optional.</span></span> <span data-ttu-id="0bf57-112">Если значение *X* отсутствует, конечная точка отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0bf57-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0bf57-113">Этот параметр должен соответствовать имени каталога для .NET Framework версии, как показано в разделе К:\виндовс\микрософт.нет\фрамеворк.</span><span class="sxs-lookup"><span data-stu-id="0bf57-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="0bf57-114">Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *x*", где *x* зависит от установленного номера сборки.</span><span class="sxs-lookup"><span data-stu-id="0bf57-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="0bf57-115">Обратите внимание, что префикс "v" является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0bf57-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="0bf57-116">[вход, выход] Указывает размер `pwzBuffer`, чтобы избежать переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="0bf57-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="0bf57-117">Если `pwzBuffer` `null`, `pchBuffer` возвращает требуемый размер `pwzBuffer`, чтобы разрешить предварительное выделение.</span><span class="sxs-lookup"><span data-stu-id="0bf57-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0bf57-118">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0bf57-118">Return Value</span></span>  
 <span data-ttu-id="0bf57-119">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="0bf57-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0bf57-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0bf57-120">HRESULT</span></span>|<span data-ttu-id="0bf57-121">Описание</span><span class="sxs-lookup"><span data-stu-id="0bf57-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0bf57-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="0bf57-122">S_OK</span></span>|<span data-ttu-id="0bf57-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="0bf57-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="0bf57-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="0bf57-124">E_POINTER</span></span>|<span data-ttu-id="0bf57-125">`pwzBuffer` или `pchBuffer` равно null.</span><span class="sxs-lookup"><span data-stu-id="0bf57-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0bf57-126">Требования</span><span class="sxs-lookup"><span data-stu-id="0bf57-126">Requirements</span></span>  
 <span data-ttu-id="0bf57-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bf57-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf57-128">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="0bf57-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0bf57-129">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0bf57-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0bf57-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf57-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf57-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0bf57-131">See also</span></span>

- [<span data-ttu-id="0bf57-132">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="0bf57-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="0bf57-133">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="0bf57-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="0bf57-134">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="0bf57-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="0bf57-135">Размещение</span><span class="sxs-lookup"><span data-stu-id="0bf57-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
