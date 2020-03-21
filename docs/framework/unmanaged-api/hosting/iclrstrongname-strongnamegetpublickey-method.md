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
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181937"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="f0a64-102">Метод ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="f0a64-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="f0a64-103">Получает открытый ключ от публичной/частной ключевой пары.</span><span class="sxs-lookup"><span data-stu-id="f0a64-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="f0a64-104">Ключевая пара может поставляться либо в качестве ключевого имени контейнера в рамках криптографического поставщика услуг (CSP), либо в виде сырой коллекции байтов.</span><span class="sxs-lookup"><span data-stu-id="f0a64-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0a64-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0a64-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0a64-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0a64-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="f0a64-107">(в) Название ключевого контейнера, содержащего публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="f0a64-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="f0a64-108">Если `pbKeyBlob` он `szKeyContainer` недействителен, необходимо указать действительный контейнер в рамках CSP.</span><span class="sxs-lookup"><span data-stu-id="f0a64-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="f0a64-109">В этом случае метод [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) извлекает общедоступный ключ из пары ключей, хранящейся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="f0a64-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="f0a64-110">Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).</span><span class="sxs-lookup"><span data-stu-id="f0a64-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="f0a64-111">Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей.</span><span class="sxs-lookup"><span data-stu-id="f0a64-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="f0a64-112">В настоящее время никакие другие типы ключей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="f0a64-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f0a64-113">(в) Указатель на публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="f0a64-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="f0a64-114">Эта пара находится в формате, `CryptExportKey` созданном функцией Win32.</span><span class="sxs-lookup"><span data-stu-id="f0a64-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="f0a64-115">Если `pbKeyBlob` он недействителен, `szKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.</span><span class="sxs-lookup"><span data-stu-id="f0a64-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f0a64-116">(в) Размер, в байтах, из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f0a64-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="f0a64-117">(ваут) Вернулся общественный ключ BLOB.</span><span class="sxs-lookup"><span data-stu-id="f0a64-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="f0a64-118">Параметр `ppbPublicKeyBlob` выделяется общим временем выполнения языка и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="f0a64-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="f0a64-119">Звонящее должно освободить память с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)</span><span class="sxs-lookup"><span data-stu-id="f0a64-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="f0a64-120">(ваут) Размер возвращенного публичного ключа BLOB.</span><span class="sxs-lookup"><span data-stu-id="f0a64-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0a64-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f0a64-121">Return Value</span></span>  
 <span data-ttu-id="f0a64-122">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="f0a64-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0a64-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="f0a64-123">Remarks</span></span>  
 <span data-ttu-id="f0a64-124">Открытый ключ содержится в структуре [PublicKeyBlob.](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)</span><span class="sxs-lookup"><span data-stu-id="f0a64-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0a64-125">Требования</span><span class="sxs-lookup"><span data-stu-id="f0a64-125">Requirements</span></span>  
 <span data-ttu-id="f0a64-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0a64-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0a64-127">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f0a64-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f0a64-128">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0a64-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0a64-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0a64-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a64-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f0a64-130">See also</span></span>

- [<span data-ttu-id="f0a64-131">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="f0a64-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="f0a64-132">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="f0a64-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="f0a64-133">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f0a64-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
