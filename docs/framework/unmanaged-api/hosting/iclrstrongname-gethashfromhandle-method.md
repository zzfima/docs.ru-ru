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
ms.openlocfilehash: 645c344e5dd9e509873a65335b5d042e94107fad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54728821"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="1cb04-102">Метод ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="1cb04-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="1cb04-103">Создает хэш содержимого файла, который имеет заданного дескриптора файла, с помощью указанного алгоритма хэширования.</span><span class="sxs-lookup"><span data-stu-id="1cb04-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cb04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1cb04-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1cb04-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1cb04-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="1cb04-106">[in] Дескриптор файла, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="1cb04-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1cb04-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="1cb04-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="1cb04-108">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1cb04-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1cb04-109">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="1cb04-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1cb04-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1cb04-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1cb04-111">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="1cb04-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cb04-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1cb04-112">Return Value</span></span>  
 <span data-ttu-id="1cb04-113">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="1cb04-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cb04-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1cb04-114">Requirements</span></span>  
 <span data-ttu-id="1cb04-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cb04-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cb04-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="1cb04-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1cb04-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1cb04-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cb04-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cb04-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb04-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1cb04-119">See also</span></span>
- [<span data-ttu-id="1cb04-120">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="1cb04-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
