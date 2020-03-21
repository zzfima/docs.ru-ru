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
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176231"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="9e249-102">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="9e249-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="9e249-103">Получает общедоступный ключ от публичной/частной пары ключей и определяет алгоритм хэша и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="9e249-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e249-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e249-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="9e249-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e249-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="9e249-106">(в) Название ключевого контейнера, содержащего публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="9e249-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="9e249-107">Если `pbKeyBlob` он `szKeyContainer` недействителен, необходимо указать действительный контейнер в рамках поставщика криптографических услуг (CSP).</span><span class="sxs-lookup"><span data-stu-id="9e249-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="9e249-108">В этом случае `StrongNameGetPublicKeyEx` метод извлекает общедоступный ключ из пары ключей, хранящейся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="9e249-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="9e249-109">Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).</span><span class="sxs-lookup"><span data-stu-id="9e249-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9e249-110">Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей.</span><span class="sxs-lookup"><span data-stu-id="9e249-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9e249-111">В настоящее время никакие другие типы ключей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="9e249-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9e249-112">(в) Указатель на публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="9e249-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9e249-113">Эта пара находится в формате, `CryptExportKey` созданном функцией Win32.</span><span class="sxs-lookup"><span data-stu-id="9e249-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9e249-114">Если `pbKeyBlob` он недействителен, `szKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.</span><span class="sxs-lookup"><span data-stu-id="9e249-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9e249-115">(в) Размер, в байтах, из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9e249-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="9e249-116">(ваут) Вернулся общественный ключ BLOB.</span><span class="sxs-lookup"><span data-stu-id="9e249-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="9e249-117">Параметр `ppbPublicKeyBlob` выделяется общим временем выполнения языка и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="9e249-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="9e249-118">Звонящее должно освободить память с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)</span><span class="sxs-lookup"><span data-stu-id="9e249-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="9e249-119">(ваут) Размер возвращенного публичного ключа BLOB.</span><span class="sxs-lookup"><span data-stu-id="9e249-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="9e249-120">(в) Алгоритм хэша сборки.</span><span class="sxs-lookup"><span data-stu-id="9e249-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="9e249-121">Список принятых значений можно осмотреть в разделе «Замечания».</span><span class="sxs-lookup"><span data-stu-id="9e249-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="9e249-122">(в) Зарезервировано для использования в будущем; по умолчанию свести на нет.</span><span class="sxs-lookup"><span data-stu-id="9e249-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e249-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9e249-123">Return Value</span></span>  
 <span data-ttu-id="9e249-124">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="9e249-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e249-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e249-125">Remarks</span></span>  
 <span data-ttu-id="9e249-126">Открытый ключ содержится в структуре [PublicKeyBlob.](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)</span><span class="sxs-lookup"><span data-stu-id="9e249-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e249-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e249-127">Remarks</span></span>  
 <span data-ttu-id="9e249-128">В следующей таблице показан набор принятых значений `uHashAlgId` для параметра.</span><span class="sxs-lookup"><span data-stu-id="9e249-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="9e249-129">Имя</span><span class="sxs-lookup"><span data-stu-id="9e249-129">Name</span></span>|<span data-ttu-id="9e249-130">Значение</span><span class="sxs-lookup"><span data-stu-id="9e249-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="9e249-131">None</span><span class="sxs-lookup"><span data-stu-id="9e249-131">None</span></span>|<span data-ttu-id="9e249-132">0</span><span class="sxs-lookup"><span data-stu-id="9e249-132">0</span></span>|  
|<span data-ttu-id="9e249-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="9e249-133">SHA-1</span></span>|<span data-ttu-id="9e249-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="9e249-134">0x8004</span></span>|  
|<span data-ttu-id="9e249-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="9e249-135">SHA-256</span></span>|<span data-ttu-id="9e249-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="9e249-136">0x800c</span></span>|  
|<span data-ttu-id="9e249-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="9e249-137">SHA-384</span></span>|<span data-ttu-id="9e249-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="9e249-138">0x800d</span></span>|  
|<span data-ttu-id="9e249-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="9e249-139">SHA-512</span></span>|<span data-ttu-id="9e249-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="9e249-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e249-141">Требования</span><span class="sxs-lookup"><span data-stu-id="9e249-141">Requirements</span></span>  
 <span data-ttu-id="9e249-142">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e249-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e249-143">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9e249-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9e249-144">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e249-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e249-145">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e249-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e249-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9e249-146">See also</span></span>

- [<span data-ttu-id="9e249-147">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="9e249-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="9e249-148">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="9e249-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="9e249-149">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9e249-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="9e249-150">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="9e249-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
