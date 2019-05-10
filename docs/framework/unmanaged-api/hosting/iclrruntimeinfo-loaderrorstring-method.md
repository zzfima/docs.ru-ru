---
title: Метод ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd7bdcf891146a15953b7466e0f6dc680495bd5a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585063"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="c9e1c-102">Метод ICLRRuntimeInfo::LoadErrorString</span><span class="sxs-lookup"><span data-stu-id="c9e1c-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="c9e1c-103">Преобразовывает значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="c9e1c-104">Этот метод замещает следующие функции:</span><span class="sxs-lookup"><span data-stu-id="c9e1c-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="c9e1c-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="c9e1c-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="c9e1c-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="c9e1c-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="c9e1c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9e1c-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9e1c-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9e1c-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="c9e1c-109">[in] Значение HRESULT, для преобразования.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="c9e1c-110">[out] Строка сообщения, связанные с данным значением HRESULT.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="c9e1c-111">[in, out] Размер `pwzbuffer` для предотвращения переполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="c9e1c-112">Если `pwzbuffer` имеет значение null, `pcchBuffer` предоставляет ожидаемый размер `pwzbuffer` чтобы разрешить предварительное выделение.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="c9e1c-113">[in] Идентификатор языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-113">[in] The culture identifier.</span></span> <span data-ttu-id="c9e1c-114">Чтобы использовать параметры по умолчанию, необходимо указать значение -1.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9e1c-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c9e1c-115">Return Value</span></span>  
 <span data-ttu-id="c9e1c-116">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c9e1c-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9e1c-117">HRESULT</span></span>|<span data-ttu-id="c9e1c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c9e1c-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9e1c-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9e1c-119">S_OK</span></span>|<span data-ttu-id="c9e1c-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="c9e1c-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c9e1c-121">E_POINTER</span></span>|<span data-ttu-id="c9e1c-122">Параметр `pcchBuffer` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="c9e1c-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="c9e1c-123">E_INVALIDARG</span></span>|<span data-ttu-id="c9e1c-124">Параметр `pwzBuffer` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="c9e1c-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c9e1c-125">Требования</span><span class="sxs-lookup"><span data-stu-id="c9e1c-125">Requirements</span></span>  
 <span data-ttu-id="c9e1c-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9e1c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9e1c-127">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c9e1c-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c9e1c-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9e1c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9e1c-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9e1c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9e1c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c9e1c-130">See also</span></span>

- [<span data-ttu-id="c9e1c-131">Интерфейс ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="c9e1c-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c9e1c-132">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c9e1c-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c9e1c-133">Размещение</span><span class="sxs-lookup"><span data-stu-id="c9e1c-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
