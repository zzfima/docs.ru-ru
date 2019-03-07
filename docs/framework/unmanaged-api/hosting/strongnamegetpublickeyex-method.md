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
ms.openlocfilehash: 5651415b9565f71e7c899996708c0b263bf0154a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487997"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="be8ae-102">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="be8ae-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="be8ae-103">Получает открытый ключ из пары открытого и закрытого ключей и определяет хэш-алгоритма и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="be8ae-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be8ae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be8ae-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="be8ae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="be8ae-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="be8ae-106">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="be8ae-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="be8ae-107">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="be8ae-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="be8ae-108">В этом случае `StrongNameGetPublicKeyEx` метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="be8ae-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="be8ae-109">Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="be8ae-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="be8ae-110">Ключи должны быть Rivest-Шамир-Adleman 1024-разрядный (RSA) ключи подписывания.</span><span class="sxs-lookup"><span data-stu-id="be8ae-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="be8ae-111">Другие типы ключей не поддерживаются в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="be8ae-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="be8ae-112">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="be8ae-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="be8ae-113">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="be8ae-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="be8ae-114">Если `pbKeyBlob` имеет значение null, контейнере ключей `szKeyContainer` предполагается, что содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="be8ae-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="be8ae-115">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="be8ae-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="be8ae-116">[out] Возвращаемый открытый ключ BLOB-ОБЪЕКТОВ.</span><span class="sxs-lookup"><span data-stu-id="be8ae-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="be8ae-117">`ppbPublicKeyBlob` Параметра выделяется, среда CLR и возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="be8ae-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="be8ae-118">Вызывающий объект должен освободить память с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="be8ae-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="be8ae-119">[out] Размер возвращаемого большой двоичный объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="be8ae-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="be8ae-120">[in] Алгоритм хеширования сборки.</span><span class="sxs-lookup"><span data-stu-id="be8ae-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="be8ae-121">См. в разделе "Примечания" для получения списка допустимых значений.</span><span class="sxs-lookup"><span data-stu-id="be8ae-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="be8ae-122">[in] Зарезервировано для будущего использования; по умолчанию null.</span><span class="sxs-lookup"><span data-stu-id="be8ae-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be8ae-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="be8ae-123">Return Value</span></span>  
 <span data-ttu-id="be8ae-124">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="be8ae-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be8ae-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="be8ae-125">Remarks</span></span>  
 <span data-ttu-id="be8ae-126">Открытый ключ, содержащийся в [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="be8ae-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be8ae-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="be8ae-127">Remarks</span></span>  
 <span data-ttu-id="be8ae-128">В следующей таблице показаны набор допустимых значений для `uHashAlgId` параметра.</span><span class="sxs-lookup"><span data-stu-id="be8ae-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="be8ae-129">name</span><span class="sxs-lookup"><span data-stu-id="be8ae-129">Name</span></span>|<span data-ttu-id="be8ae-130">Значение</span><span class="sxs-lookup"><span data-stu-id="be8ae-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="be8ae-131">Нет</span><span class="sxs-lookup"><span data-stu-id="be8ae-131">None</span></span>|<span data-ttu-id="be8ae-132">0</span><span class="sxs-lookup"><span data-stu-id="be8ae-132">0</span></span>|  
|<span data-ttu-id="be8ae-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="be8ae-133">SHA-1</span></span>|<span data-ttu-id="be8ae-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="be8ae-134">0x8004</span></span>|  
|<span data-ttu-id="be8ae-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="be8ae-135">SHA-256</span></span>|<span data-ttu-id="be8ae-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="be8ae-136">0x800c</span></span>|  
|<span data-ttu-id="be8ae-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="be8ae-137">SHA-384</span></span>|<span data-ttu-id="be8ae-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="be8ae-138">0x800d</span></span>|  
|<span data-ttu-id="be8ae-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="be8ae-139">SHA-512</span></span>|<span data-ttu-id="be8ae-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="be8ae-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be8ae-141">Требования</span><span class="sxs-lookup"><span data-stu-id="be8ae-141">Requirements</span></span>  
 <span data-ttu-id="be8ae-142">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be8ae-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be8ae-143">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="be8ae-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="be8ae-144">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="be8ae-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be8ae-145">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be8ae-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be8ae-146">См. также</span><span class="sxs-lookup"><span data-stu-id="be8ae-146">See also</span></span>
- [<span data-ttu-id="be8ae-147">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="be8ae-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="be8ae-148">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="be8ae-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="be8ae-149">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="be8ae-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="be8ae-150">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="be8ae-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
