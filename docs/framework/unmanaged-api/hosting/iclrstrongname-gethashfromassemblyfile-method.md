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
ms.openlocfilehash: b6d5ea24e40357205051188b68de8b973d2cec18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748244"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="f5f83-102">Метод ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="f5f83-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="f5f83-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="f5f83-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5f83-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5f83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5f83-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f5f83-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="f5f83-106">[in] Путь к файлу, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="f5f83-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f5f83-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="f5f83-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f5f83-108">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5f83-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f5f83-109">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="f5f83-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f5f83-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f5f83-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f5f83-111">[out] Размер в байтах, возвращенное `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f5f83-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5f83-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f5f83-112">Return Value</span></span>  
 <span data-ttu-id="f5f83-113">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="f5f83-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5f83-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f5f83-114">Requirements</span></span>  
 <span data-ttu-id="f5f83-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5f83-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5f83-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f5f83-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f5f83-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5f83-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5f83-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5f83-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5f83-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f5f83-119">See also</span></span>

- [<span data-ttu-id="f5f83-120">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="f5f83-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="f5f83-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f5f83-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
