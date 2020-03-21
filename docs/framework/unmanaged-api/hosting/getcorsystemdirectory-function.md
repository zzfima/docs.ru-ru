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
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178207"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="b392f-102">Функция GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="b392f-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="b392f-103">Возвращает каталог установки общего времени выполнения языка (CLR), который загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="b392f-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="b392f-104">Каталог установки полностью квалифицирован, например, "c: »окна »microsoft.net» framework-v1.0.3705.</span><span class="sxs-lookup"><span data-stu-id="b392f-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="b392f-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b392f-105">This function is deprecated.</span></span> <span data-ttu-id="b392f-106">Он заменяется методом [ICLRRuntimeInfo::GetRuntimeDirectory,](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) представленным в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="b392f-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b392f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b392f-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="b392f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="b392f-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="b392f-109">(ваут) Буфер, в котором время выполнения возвращает строку, содержащую полностью квалифицированное название каталога установки для времени выполнения, загруженного в процесс.</span><span class="sxs-lookup"><span data-stu-id="b392f-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="b392f-110">Если время выполнения еще не загружено в процесс, функция возвращает соответствующую информацию каталога для последней версии времени выполнения, установленной на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b392f-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="b392f-111">(в) Размер, в байтах, из `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="b392f-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b392f-112">(ваут) Количество символов, возвращенных в `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="b392f-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b392f-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="b392f-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b392f-114">Не используйте эту функцию в процессах, которые работают версия 4 CLR.</span><span class="sxs-lookup"><span data-stu-id="b392f-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="b392f-115">Если более ранняя версия CLR установлена на компьютере, эта функция возвращает каталог установки для этой версии.</span><span class="sxs-lookup"><span data-stu-id="b392f-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b392f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b392f-116">Requirements</span></span>  
 <span data-ttu-id="b392f-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b392f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b392f-118">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b392f-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b392f-119">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b392f-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b392f-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b392f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b392f-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b392f-121">See also</span></span>

- [<span data-ttu-id="b392f-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="b392f-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
