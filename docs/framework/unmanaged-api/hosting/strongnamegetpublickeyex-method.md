---
title: Метод StrongNameGetPublicKeyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82dbacdcf89a44455bb4963e73dc5e91bda1cbc7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43482454"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="67c34-102">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="67c34-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="67c34-103">Получает открытый ключ из пары открытого и закрытого ключей и определяет хэш-алгоритма и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="67c34-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67c34-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67c34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67c34-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="67c34-106">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="67c34-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="67c34-107">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="67c34-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="67c34-108">В этом случае `StrongNameGetPublicKeyEx` метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="67c34-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="67c34-109">Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="67c34-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="67c34-110">Ключи должны быть Rivest-Шамир-Adleman 1024-разрядный (RSA) ключи подписывания.</span><span class="sxs-lookup"><span data-stu-id="67c34-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="67c34-111">Другие типы ключей не поддерживаются в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="67c34-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="67c34-112">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="67c34-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="67c34-113">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="67c34-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="67c34-114">Если `pbKeyBlob` имеет значение null, контейнере ключей `szKeyContainer` предполагается, что содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="67c34-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="67c34-115">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="67c34-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="67c34-116">[out] Возвращаемый открытый ключ BLOB-ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="67c34-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="67c34-117">`ppbPublicKeyBlob` Параметра выделяется, среда CLR и возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="67c34-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="67c34-118">Вызывающий объект должен освободить память с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="67c34-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="67c34-119">[out] Размер возвращаемого большой двоичный объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="67c34-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="67c34-120">[in] Алгоритм хеширования сборки.</span><span class="sxs-lookup"><span data-stu-id="67c34-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="67c34-121">См. в разделе "Примечания" для получения списка допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="67c34-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="67c34-122">[in] Зарезервировано для будущего использования; по умолчанию null.</span><span class="sxs-lookup"><span data-stu-id="67c34-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67c34-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="67c34-123">Return Value</span></span>  
 <span data-ttu-id="67c34-124">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="67c34-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c34-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="67c34-125">Remarks</span></span>  
 <span data-ttu-id="67c34-126">Открытый ключ, содержащийся в [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="67c34-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c34-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="67c34-127">Remarks</span></span>  
 <span data-ttu-id="67c34-128">В следующей таблице показаны набор допустимых значений для `uHashAlgId` параметра.</span><span class="sxs-lookup"><span data-stu-id="67c34-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="67c34-129">name</span><span class="sxs-lookup"><span data-stu-id="67c34-129">Name</span></span>|<span data-ttu-id="67c34-130">Значение</span><span class="sxs-lookup"><span data-stu-id="67c34-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="67c34-131">Нет</span><span class="sxs-lookup"><span data-stu-id="67c34-131">None</span></span>|<span data-ttu-id="67c34-132">0</span><span class="sxs-lookup"><span data-stu-id="67c34-132">0</span></span>|  
|<span data-ttu-id="67c34-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="67c34-133">SHA-1</span></span>|<span data-ttu-id="67c34-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="67c34-134">0x8004</span></span>|  
|<span data-ttu-id="67c34-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="67c34-135">SHA-256</span></span>|<span data-ttu-id="67c34-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="67c34-136">0x800c</span></span>|  
|<span data-ttu-id="67c34-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="67c34-137">SHA-384</span></span>|<span data-ttu-id="67c34-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="67c34-138">0x800d</span></span>|  
|<span data-ttu-id="67c34-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="67c34-139">SHA-512</span></span>|<span data-ttu-id="67c34-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="67c34-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67c34-141">Требования</span><span class="sxs-lookup"><span data-stu-id="67c34-141">Requirements</span></span>  
 <span data-ttu-id="67c34-142">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c34-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c34-143">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="67c34-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="67c34-144">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="67c34-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="67c34-145">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c34-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c34-146">См. также</span><span class="sxs-lookup"><span data-stu-id="67c34-146">See Also</span></span>  
 [<span data-ttu-id="67c34-147">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="67c34-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="67c34-148">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="67c34-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [<span data-ttu-id="67c34-149">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="67c34-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="67c34-150">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="67c34-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
