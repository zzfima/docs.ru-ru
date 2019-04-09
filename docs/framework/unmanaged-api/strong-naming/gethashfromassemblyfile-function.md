---
title: Функция GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56a509d08b19cf449177984e7b59481eb7b09a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092166"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="5d449-102">Функция GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="5d449-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="5d449-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="5d449-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="5d449-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="5d449-104">This function has been deprecated.</span></span> <span data-ttu-id="5d449-105">Используйте [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="5d449-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d449-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d449-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d449-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d449-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="5d449-108">[in] Путь к файлу, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="5d449-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5d449-109">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="5d449-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5d449-110">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5d449-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5d449-111">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="5d449-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5d449-112">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="5d449-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5d449-113">[out] Размер в байтах, возвращенное `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="5d449-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d449-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5d449-114">Requirements</span></span>  
 <span data-ttu-id="5d449-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d449-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d449-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5d449-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5d449-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d449-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5d449-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5d449-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d449-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5d449-119">See also</span></span>

- [<span data-ttu-id="5d449-120">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="5d449-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="5d449-121">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="5d449-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="5d449-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5d449-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
