---
title: Метод ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8d9e7d593c2a8a9cce798724b2705dee21a740e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075165"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="700ec-102">Метод ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="700ec-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="700ec-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="700ec-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="700ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="700ec-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="700ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="700ec-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="700ec-106">[in] Путь к файлу, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="700ec-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="700ec-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="700ec-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="700ec-108">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="700ec-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="700ec-109">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="700ec-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="700ec-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="700ec-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="700ec-111">[out] Размер в байтах, возвращенное `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="700ec-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="700ec-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="700ec-112">Return Value</span></span>  
 <span data-ttu-id="700ec-113">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="700ec-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="700ec-114">Требования</span><span class="sxs-lookup"><span data-stu-id="700ec-114">Requirements</span></span>  
 <span data-ttu-id="700ec-115">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="700ec-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="700ec-116">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="700ec-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="700ec-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="700ec-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="700ec-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="700ec-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="700ec-119">См. также</span><span class="sxs-lookup"><span data-stu-id="700ec-119">See Also</span></span>  
 [<span data-ttu-id="700ec-120">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="700ec-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="700ec-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="700ec-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
