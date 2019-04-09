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
ms.openlocfilehash: 6d11c71498053844792cd902959dee642877c46b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146982"
---
# <a name="iclrstrongnamegethashfromhandle-method"></a><span data-ttu-id="f2b5c-102">Метод ICLRStrongName::GetHashFromHandle</span><span class="sxs-lookup"><span data-stu-id="f2b5c-102">ICLRStrongName::GetHashFromHandle Method</span></span>
<span data-ttu-id="f2b5c-103">Создает хэш содержимого файла, который имеет заданного дескриптора файла, с помощью указанного алгоритма хэширования.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-103">Generates a hash over the contents of the file that has the specified file handle, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2b5c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2b5c-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2b5c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2b5c-105">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f2b5c-106">[in] Дескриптор файла, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-106">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f2b5c-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f2b5c-108">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-108">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f2b5c-109">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f2b5c-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f2b5c-111">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f2b5c-111">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2b5c-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f2b5c-112">Return Value</span></span>  
 `S_OK` <span data-ttu-id="f2b5c-113">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="f2b5c-113">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2b5c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f2b5c-114">Requirements</span></span>  
 <span data-ttu-id="f2b5c-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2b5c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2b5c-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f2b5c-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f2b5c-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2b5c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f2b5c-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f2b5c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2b5c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f2b5c-119">See also</span></span>

- [<span data-ttu-id="f2b5c-120">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f2b5c-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
