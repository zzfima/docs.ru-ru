---
title: Метод ICLRStrongName::StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 203c8647366952b1d58799b97dfd53aea22859ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992801"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="28f0d-102">Метод ICLRStrongName::StrongNameTokenFromAssemblyEx</span><span class="sxs-lookup"><span data-stu-id="28f0d-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="28f0d-103">Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ, представляющий токен.</span><span class="sxs-lookup"><span data-stu-id="28f0d-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28f0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28f0d-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28f0d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="28f0d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="28f0d-106">[in] Путь к переносимого исполняемого (PE) файла для сборки.</span><span class="sxs-lookup"><span data-stu-id="28f0d-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="28f0d-107">[out] Токен, возвращенный строгого имени.</span><span class="sxs-lookup"><span data-stu-id="28f0d-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="28f0d-108">[out] Размер в байтах, строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="28f0d-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="28f0d-109">[out] Возвращаемый открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="28f0d-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="28f0d-110">[out] Размер в байтах, открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="28f0d-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28f0d-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="28f0d-111">Return Value</span></span>  
 <span data-ttu-id="28f0d-112">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="28f0d-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28f0d-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="28f0d-113">Remarks</span></span>  
 <span data-ttu-id="28f0d-114">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="28f0d-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="28f0d-115">Токен является 64-разрядный хэш, который создается из открытого ключа, используемого для подписания сборки.</span><span class="sxs-lookup"><span data-stu-id="28f0d-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="28f0d-116">Маркер является частью строгого имени для сборки и может быть считано из метаданных сборки.</span><span class="sxs-lookup"><span data-stu-id="28f0d-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="28f0d-117">После извлечения ключа и создания маркера, необходимо вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="28f0d-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28f0d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="28f0d-118">Requirements</span></span>  
 <span data-ttu-id="28f0d-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28f0d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28f0d-120">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="28f0d-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="28f0d-121">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28f0d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28f0d-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28f0d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28f0d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="28f0d-123">See also</span></span>

- [<span data-ttu-id="28f0d-124">Метод StrongNameTokenFromAssembly</span><span class="sxs-lookup"><span data-stu-id="28f0d-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="28f0d-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="28f0d-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
