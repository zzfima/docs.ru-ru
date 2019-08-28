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
ms.openlocfilehash: d30384ea8b9ff4eee41abd43ae39486f770039e7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041426"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="c3fa0-102">Функция GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="c3fa0-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="c3fa0-103">Возвращает каталог установки среды CLR, который загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="c3fa0-104">Каталог установки полностью квалифицирован, например "c:\windows\microsoft.net\framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="c3fa0-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="c3fa0-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-105">This function is deprecated.</span></span> <span data-ttu-id="c3fa0-106">Он заменяется методом [ICLRRuntimeInfo:: GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) , предоставленным в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3fa0-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3fa0-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (   
    [out] LPWSTR  pbuffer,     
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c3fa0-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3fa0-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="c3fa0-109">заполняет Буфер, в котором среда выполнения возвращает строку, содержащую полное имя каталога установки для среды выполнения, которая загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="c3fa0-110">Если среда выполнения еще не загружена в процесс, функция возвращает соответствующие сведения о каталоге для последней версии среды выполнения, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c3fa0-111">окне Размер (в байтах `pbuffer`).</span><span class="sxs-lookup"><span data-stu-id="c3fa0-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c3fa0-112">заполняет Число символов, возвращаемых в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3fa0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3fa0-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="c3fa0-114">Не используйте эту функцию в процессах, работающих в среде CLR версии 4.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="c3fa0-115">Если на компьютере установлена более ранняя версия среды CLR, эта функция возвращает каталог установки для этой версии.</span><span class="sxs-lookup"><span data-stu-id="c3fa0-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3fa0-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c3fa0-116">Requirements</span></span>  
 <span data-ttu-id="c3fa0-117">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3fa0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3fa0-118">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c3fa0-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3fa0-119">**Библиотечная** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c3fa0-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3fa0-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3fa0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3fa0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c3fa0-121">See also</span></span>

- [<span data-ttu-id="c3fa0-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c3fa0-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
