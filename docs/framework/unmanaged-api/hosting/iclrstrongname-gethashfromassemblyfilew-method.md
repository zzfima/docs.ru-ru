---
title: Метод ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36e4f07f04968579be2e42efad666b0453cc4796
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434795"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="431c9-102">Метод ICLRStrongName::GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="431c9-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="431c9-103">Создает хэш содержимого файла, заданный строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="431c9-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="431c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="431c9-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="431c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="431c9-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="431c9-106">[in] Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="431c9-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="431c9-107">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="431c9-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="431c9-108">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="431c9-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="431c9-109">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="431c9-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="431c9-110">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="431c9-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="431c9-111">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="431c9-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="431c9-112">[out] Возвращаемый размер в байтах для `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="431c9-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="431c9-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="431c9-113">Return Value</span></span>  
 <span data-ttu-id="431c9-114">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="431c9-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="431c9-115">Требования</span><span class="sxs-lookup"><span data-stu-id="431c9-115">Requirements</span></span>  
 <span data-ttu-id="431c9-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="431c9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="431c9-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="431c9-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="431c9-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="431c9-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="431c9-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="431c9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431c9-120">См. также</span><span class="sxs-lookup"><span data-stu-id="431c9-120">See Also</span></span>  
 [<span data-ttu-id="431c9-121">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="431c9-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="431c9-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="431c9-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
