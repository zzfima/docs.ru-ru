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
ms.openlocfilehash: b772de720a8c3b669bd3cbe9591637d931cb8763
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430623"
---
# <a name="getfileversion-function"></a><span data-ttu-id="7447c-102">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="7447c-102">GetFileVersion Function</span></span>
<span data-ttu-id="7447c-103">Возвращает общий язык среды выполнения (CLR) сведения о версии указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="7447c-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="7447c-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7447c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7447c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7447c-105">Syntax</span></span>  
  
```  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7447c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7447c-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="7447c-107">[in] Путь к файлу, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="7447c-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="7447c-108">[in, out] Буфер, выделенный для сведения о версии, который возвращается.</span><span class="sxs-lookup"><span data-stu-id="7447c-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7447c-109">[in] Размер в расширенные символы из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="7447c-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="7447c-110">[out] Размер в байтах, возвращаемого `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="7447c-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7447c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7447c-111">Requirements</span></span>  
 <span data-ttu-id="7447c-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7447c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7447c-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7447c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7447c-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7447c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7447c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7447c-115">See Also</span></span>  
 [<span data-ttu-id="7447c-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="7447c-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
