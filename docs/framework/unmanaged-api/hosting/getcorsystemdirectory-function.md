---
title: Функция GetCORSystemDirectory
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 567e6533a9a9ac718f8b5acac769295c104f7f3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144330"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="9f98a-102">Функция GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="9f98a-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="9f98a-103">Возвращает каталог установки среда CLR (CLR), который загружается процесс.</span><span class="sxs-lookup"><span data-stu-id="9f98a-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="9f98a-104">Каталог установки — полное имя, например, «c:\windows\microsoft.net\framework\v1.0.3705».</span><span class="sxs-lookup"><span data-stu-id="9f98a-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="9f98a-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9f98a-105">This function is deprecated.</span></span> <span data-ttu-id="9f98a-106">Он заменен [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) метода [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f98a-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f98a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f98a-107">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="9f98a-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="9f98a-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="9f98a-109">[out] Буфер, в котором среда выполнения возвращает строку, содержащую полное имя каталога установки для среды выполнения, который загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="9f98a-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="9f98a-110">Если среда выполнения еще не был загружен в процесс, функция возвращает данные каталога, соответствующего для последней версии среды выполнения, установленную на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f98a-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9f98a-111">[in] Размер в байтах из `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="9f98a-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9f98a-112">[out] Число символов, возвращаемых в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="9f98a-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f98a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f98a-113">Remarks</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9f98a-114">Не используйте эту функцию в процессах, работающих под управлением версии 4 среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9f98a-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="9f98a-115">Если на компьютере установлена более ранняя версия среды CLR, эта функция возвращает каталог установки этой версии.</span><span class="sxs-lookup"><span data-stu-id="9f98a-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f98a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9f98a-116">Requirements</span></span>  
 <span data-ttu-id="9f98a-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f98a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f98a-118">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9f98a-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9f98a-119">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f98a-119">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9f98a-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9f98a-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9f98a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9f98a-121">See also</span></span>

- [<span data-ttu-id="9f98a-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="9f98a-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
