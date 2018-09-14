---
title: Метод ICLRStrongName::GetHashFromHandle
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromHandle
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromHandle method [.NET Framework hosting]
ms.assetid: 3bedbb7d-3cdd-4175-b370-10ae734062db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20c5f6bbb58b85f42ec00e356eccc5fb41ce813c
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591598"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="0dcd7-102">Метод ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="0dcd7-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="0dcd7-103">Создает хэш содержимого файла, который имеет заданного дескриптора файла, с помощью указанного алгоритма хэширования.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dcd7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0dcd7-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0dcd7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0dcd7-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="0dcd7-106">[in] Дескриптор файла, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="0dcd7-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="0dcd7-108">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="0dcd7-109">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="0dcd7-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="0dcd7-111">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0dcd7-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0dcd7-112">Return Value</span></span>  
 <span data-ttu-id="0dcd7-113">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="0dcd7-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dcd7-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0dcd7-114">Requirements</span></span>  
 <span data-ttu-id="0dcd7-115">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dcd7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dcd7-116">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0dcd7-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0dcd7-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0dcd7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0dcd7-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dcd7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcd7-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0dcd7-119">See Also</span></span>  
 [<span data-ttu-id="0dcd7-120">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0dcd7-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
