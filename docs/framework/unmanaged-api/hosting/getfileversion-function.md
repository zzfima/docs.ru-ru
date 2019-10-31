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
ms.openlocfilehash: f197c8802bd9e55391b3e3e20c64398736070a16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136338"
---
# <a name="getfileversion-function"></a><span data-ttu-id="52a89-102">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="52a89-102">GetFileVersion Function</span></span>
<span data-ttu-id="52a89-103">Возвращает сведения о версии среды CLR указанного файла, используя указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="52a89-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="52a89-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="52a89-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52a89-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52a89-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52a89-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="52a89-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="52a89-107">окне Путь к файлу, который необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="52a89-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="52a89-108">[вход, выход] Буфер, выделенный для возвращаемой информации о версии.</span><span class="sxs-lookup"><span data-stu-id="52a89-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="52a89-109">окне Размер в расширенных символах `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="52a89-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="52a89-110">заполняет Размер возвращаемого `szBuffer`в байтах.</span><span class="sxs-lookup"><span data-stu-id="52a89-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52a89-111">Требования</span><span class="sxs-lookup"><span data-stu-id="52a89-111">Requirements</span></span>  
 <span data-ttu-id="52a89-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52a89-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52a89-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="52a89-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52a89-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52a89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52a89-115">См. также</span><span class="sxs-lookup"><span data-stu-id="52a89-115">See also</span></span>

- [<span data-ttu-id="52a89-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="52a89-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
