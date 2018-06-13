---
title: Метод ICLRStrongName::StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b736e58a1a48a2bb4492b6b8ff58af1567babcf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434484"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="a91f9-102">Метод ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a91f9-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="a91f9-103">Возвращает открытый ключ из пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="a91f9-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="a91f9-104">Пара ключей может предоставляться в виде имени контейнера ключей в поставщике служб шифрования (CSP) или как коллекция необработанных байтов.</span><span class="sxs-lookup"><span data-stu-id="a91f9-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a91f9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a91f9-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a91f9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a91f9-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="a91f9-107">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="a91f9-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="a91f9-108">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб Шифрования.</span><span class="sxs-lookup"><span data-stu-id="a91f9-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="a91f9-109">В этом случае [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="a91f9-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="a91f9-110">Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="a91f9-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a91f9-111">Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания.</span><span class="sxs-lookup"><span data-stu-id="a91f9-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a91f9-112">Другие типы ключей не поддерживаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a91f9-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a91f9-113">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="a91f9-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a91f9-114">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="a91f9-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a91f9-115">Если `pbKeyBlob` равен null, контейнер ключей, заданные `szKeyContainer` должна содержать пары ключей.</span><span class="sxs-lookup"><span data-stu-id="a91f9-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a91f9-116">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a91f9-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="a91f9-117">[out] Возвращаемый открытый ключ большого двоичного ОБЪЕКТА.</span><span class="sxs-lookup"><span data-stu-id="a91f9-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="a91f9-118">`ppbPublicKeyBlob` Параметра выделяется средой CLR и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="a91f9-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="a91f9-119">Вызывающий объект должен освободить память с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a91f9-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="a91f9-120">[out] Размер возвращаемого BLOB-объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="a91f9-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a91f9-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a91f9-121">Return Value</span></span>  
 <span data-ttu-id="a91f9-122">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="a91f9-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a91f9-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="a91f9-123">Remarks</span></span>  
 <span data-ttu-id="a91f9-124">Открытый ключ содержится в [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="a91f9-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a91f9-125">Требования</span><span class="sxs-lookup"><span data-stu-id="a91f9-125">Requirements</span></span>  
 <span data-ttu-id="a91f9-126">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a91f9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a91f9-127">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a91f9-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a91f9-128">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a91f9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a91f9-129">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a91f9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a91f9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a91f9-130">See Also</span></span>  
 [<span data-ttu-id="a91f9-131">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="a91f9-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="a91f9-132">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="a91f9-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="a91f9-133">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a91f9-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
