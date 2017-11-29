---
title: "Метод ICLRStrongName::StrongNameTokenFromAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b236fe3b041277401c2983cf229981253c01328
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="27d7c-102">Метод ICLRStrongName::StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="27d7c-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="27d7c-103">Создает маркер строгого имени из указанного файла сборки.</span><span class="sxs-lookup"><span data-stu-id="27d7c-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d7c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27d7c-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="27d7c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27d7c-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="27d7c-106">[in] Путь к файлу переносимого исполняемого (PE) для сборки.</span><span class="sxs-lookup"><span data-stu-id="27d7c-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="27d7c-107">[out] Возвращаемый строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="27d7c-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="27d7c-108">[out] Размер в байтах строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="27d7c-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27d7c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27d7c-109">Return Value</span></span>  
 <span data-ttu-id="27d7c-110">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="27d7c-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27d7c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="27d7c-111">Remarks</span></span>  
 <span data-ttu-id="27d7c-112">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="27d7c-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="27d7c-113">Маркер является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="27d7c-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="27d7c-114">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="27d7c-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="27d7c-115">После создания маркера необходимо вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="27d7c-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27d7c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="27d7c-116">Requirements</span></span>  
 <span data-ttu-id="27d7c-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27d7c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27d7c-118">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="27d7c-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="27d7c-119">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27d7c-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27d7c-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27d7c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d7c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="27d7c-121">See Also</span></span>  
 [<span data-ttu-id="27d7c-122">Метод StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="27d7c-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="27d7c-123">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="27d7c-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
