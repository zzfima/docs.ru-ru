---
title: Функция GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 349604404487501a692b9a2472ed32878c62d879
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494812"
---
# <a name="getfileversion-function"></a><span data-ttu-id="49826-102">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="49826-102">GetFileVersion Function</span></span>
<span data-ttu-id="49826-103">Получает информация среды CLR (CLR) версии указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="49826-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="49826-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49826-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49826-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49826-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49826-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="49826-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="49826-107">[in] Путь к файлу, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="49826-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="49826-108">[in, out] Буфер, выделенный для сведений о версии, который возвращается.</span><span class="sxs-lookup"><span data-stu-id="49826-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="49826-109">[in] Размер в расширенные символы из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="49826-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="49826-110">[out] Размер в байтах, возвращаемого `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="49826-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49826-111">Требования</span><span class="sxs-lookup"><span data-stu-id="49826-111">Requirements</span></span>  
 <span data-ttu-id="49826-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49826-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49826-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="49826-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49826-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49826-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49826-115">См. также</span><span class="sxs-lookup"><span data-stu-id="49826-115">See also</span></span>
- [<span data-ttu-id="49826-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="49826-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
