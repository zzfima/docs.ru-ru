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
ms.openlocfilehash: 714827da24b3fc0a334210fd94e61f80cb2afe49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993113"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="5fc67-102">Метод ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="5fc67-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="5fc67-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="5fc67-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fc67-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fc67-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fc67-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fc67-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="5fc67-106">[in] Путь к файлу, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="5fc67-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5fc67-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="5fc67-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5fc67-108">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5fc67-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5fc67-109">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="5fc67-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5fc67-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="5fc67-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5fc67-111">[out] Размер в байтах, возвращенное `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="5fc67-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fc67-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5fc67-112">Return Value</span></span>  
 <span data-ttu-id="5fc67-113">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="5fc67-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fc67-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5fc67-114">Requirements</span></span>  
 <span data-ttu-id="5fc67-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fc67-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fc67-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5fc67-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5fc67-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5fc67-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fc67-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fc67-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fc67-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5fc67-119">See also</span></span>

- [<span data-ttu-id="5fc67-120">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="5fc67-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="5fc67-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5fc67-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
