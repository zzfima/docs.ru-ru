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
ms.openlocfilehash: f3b51c1b376fa9c664de53aa76ec724ca305ae6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178181"
---
# <a name="getfileversion-function"></a><span data-ttu-id="0d182-102">Функция GetFileVersion</span><span class="sxs-lookup"><span data-stu-id="0d182-102">GetFileVersion Function</span></span>
<span data-ttu-id="0d182-103">Получает информацию о версии общего времени выполнения языка (CLR) указанного файла с использованием указанного буфера.</span><span class="sxs-lookup"><span data-stu-id="0d182-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="0d182-104">Эта функция была унесена в системе .NET 4.</span><span class="sxs-lookup"><span data-stu-id="0d182-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d182-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d182-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d182-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d182-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="0d182-107">(в) Путь изучения файла.</span><span class="sxs-lookup"><span data-stu-id="0d182-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="0d182-108">(в, вне) Буфер, выделенный для возвращенной информации версии.</span><span class="sxs-lookup"><span data-stu-id="0d182-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0d182-109">(в) Размер, в широких символов, из `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d182-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="0d182-110">(ваут) Размер, в байтах, `szBuffer`возвращенного .</span><span class="sxs-lookup"><span data-stu-id="0d182-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d182-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0d182-111">Requirements</span></span>  
 <span data-ttu-id="0d182-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d182-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d182-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d182-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d182-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d182-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d182-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0d182-115">See also</span></span>

- [<span data-ttu-id="0d182-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="0d182-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
