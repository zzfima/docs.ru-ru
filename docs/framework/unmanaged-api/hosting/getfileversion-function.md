---
title: "Функция GetFileVersion"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43e7a1326cad1b831a88c7fc3877679b4c096709
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getfileversion-function"></a><span data-ttu-id="7abc7-102">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="7abc7-102">GetFileVersion Function</span></span>
<span data-ttu-id="7abc7-103">Возвращает общий язык среды выполнения (CLR) сведения о версии указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="7abc7-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="7abc7-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7abc7-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7abc7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7abc7-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7abc7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7abc7-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="7abc7-107">[in] Путь к файлу, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="7abc7-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="7abc7-108">[in, out] Буфер, выделенный для сведения о версии, который возвращается.</span><span class="sxs-lookup"><span data-stu-id="7abc7-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7abc7-109">[in] Размер в расширенные символы из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="7abc7-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7abc7-110">[out] Размер в байтах, возвращаемого `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="7abc7-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7abc7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7abc7-111">Requirements</span></span>  
 <span data-ttu-id="7abc7-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7abc7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7abc7-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7abc7-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7abc7-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7abc7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7abc7-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7abc7-115">See Also</span></span>  
 [<span data-ttu-id="7abc7-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="7abc7-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
