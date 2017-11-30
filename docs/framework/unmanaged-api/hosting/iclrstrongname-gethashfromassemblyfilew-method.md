---
title: "Метод ICLRStrongName::GetHashFromAssemblyFileW"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFileW
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 14b4e6dae97777873f458018acdaf0c3f5d4f070
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a><span data-ttu-id="b728b-102">Метод ICLRStrongName::GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="b728b-102">ICLRStrongName::GetHashFromAssemblyFileW Method</span></span>
<span data-ttu-id="b728b-103">Создает хэш содержимого файла, заданный строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="b728b-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b728b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b728b-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b728b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b728b-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b728b-106">[in] Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="b728b-106">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="b728b-107">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="b728b-107">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="b728b-108">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="b728b-108">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="b728b-109">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b728b-109">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="b728b-110">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="b728b-110">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="b728b-111">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="b728b-111">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="b728b-112">[out] Возвращаемый размер в байтах для `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="b728b-112">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b728b-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b728b-113">Return Value</span></span>  
 <span data-ttu-id="b728b-114">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="b728b-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b728b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b728b-115">Requirements</span></span>  
 <span data-ttu-id="b728b-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b728b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b728b-117">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b728b-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b728b-118">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b728b-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b728b-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b728b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b728b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b728b-120">See Also</span></span>  
 [<span data-ttu-id="b728b-121">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="b728b-121">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="b728b-122">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b728b-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
