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
ms.openlocfilehash: 83e3ba8644af1f630b5c9ad5268ec44750badc88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682068"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="6bc40-102">Функция GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="6bc40-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="6bc40-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="6bc40-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="6bc40-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="6bc40-104">This function has been deprecated.</span></span> <span data-ttu-id="6bc40-105">Используйте [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="6bc40-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc40-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bc40-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6bc40-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bc40-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="6bc40-108">[in] Путь к файлу, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="6bc40-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="6bc40-109">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="6bc40-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="6bc40-110">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6bc40-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="6bc40-111">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="6bc40-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="6bc40-112">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="6bc40-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="6bc40-113">[out] Размер в байтах, возвращенное `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="6bc40-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bc40-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6bc40-114">Requirements</span></span>  
 <span data-ttu-id="6bc40-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bc40-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bc40-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6bc40-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6bc40-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bc40-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6bc40-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bc40-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc40-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6bc40-119">See also</span></span>
- [<span data-ttu-id="6bc40-120">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="6bc40-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="6bc40-121">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="6bc40-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="6bc40-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="6bc40-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
