---
title: "Метод ICLRStrongName::GetHashFromAssemblyFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9a205f4225269f959efec9576bea047fb51ea946
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a><span data-ttu-id="18314-102">Метод ICLRStrongName::GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="18314-102">ICLRStrongName::GetHashFromAssemblyFile Method</span></span>
<span data-ttu-id="18314-103">Возвращает хэш файла указанную сборку, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="18314-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18314-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18314-104">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18314-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="18314-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="18314-106">[in] Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="18314-106">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="18314-107">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="18314-107">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="18314-108">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="18314-108">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="18314-109">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="18314-109">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="18314-110">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="18314-110">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="18314-111">[out] Возвращаемый размер в байтах для `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="18314-111">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18314-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18314-112">Return Value</span></span>  
 <span data-ttu-id="18314-113">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="18314-113">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18314-114">Требования</span><span class="sxs-lookup"><span data-stu-id="18314-114">Requirements</span></span>  
 <span data-ttu-id="18314-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18314-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18314-116">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="18314-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="18314-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18314-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18314-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18314-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18314-119">См. также</span><span class="sxs-lookup"><span data-stu-id="18314-119">See Also</span></span>  
 [<span data-ttu-id="18314-120">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="18314-120">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="18314-121">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="18314-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
