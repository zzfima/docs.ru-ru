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
ms.openlocfilehash: 834292192aa447a113372bc8807041954b39a115
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937773"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="21aaa-102">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="21aaa-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="21aaa-103">Получает открытый ключ из пары открытого и закрытого ключей и задает алгоритм хеширования и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="21aaa-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21aaa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21aaa-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="21aaa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="21aaa-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="21aaa-106">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="21aaa-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="21aaa-107">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="21aaa-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="21aaa-108">В этом случае метод `StrongNameGetPublicKeyEx` извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="21aaa-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="21aaa-109">Если `pbKeyBlob` не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="21aaa-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="21aaa-110">Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA).</span><span class="sxs-lookup"><span data-stu-id="21aaa-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="21aaa-111">В настоящее время не поддерживаются никакие другие типы ключей.</span><span class="sxs-lookup"><span data-stu-id="21aaa-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="21aaa-112">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="21aaa-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="21aaa-113">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="21aaa-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="21aaa-114">Если `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром `szKeyContainer`, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="21aaa-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="21aaa-115">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="21aaa-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="21aaa-116">заполняет Возвращенный большой двоичный объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="21aaa-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="21aaa-117">Параметр `ppbPublicKeyBlob` выделяется средой CLR и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="21aaa-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="21aaa-118">Вызывающий объект должен освободить память с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="21aaa-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="21aaa-119">заполняет Размер возвращенного большого двоичного объекта открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="21aaa-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="21aaa-120">окне Хэш-алгоритм сборки.</span><span class="sxs-lookup"><span data-stu-id="21aaa-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="21aaa-121">Список допустимых значений см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="21aaa-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="21aaa-122">окне Зарезервировано для будущего использования; по умолчанию принимает значение null.</span><span class="sxs-lookup"><span data-stu-id="21aaa-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21aaa-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="21aaa-123">Return Value</span></span>  
 <span data-ttu-id="21aaa-124">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="21aaa-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21aaa-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="21aaa-125">Remarks</span></span>  
 <span data-ttu-id="21aaa-126">Открытый ключ содержится в структуре [публиккэйблоб](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="21aaa-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21aaa-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="21aaa-127">Remarks</span></span>  
 <span data-ttu-id="21aaa-128">В следующей таблице показан набор допустимых значений для параметра `uHashAlgId`.</span><span class="sxs-lookup"><span data-stu-id="21aaa-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="21aaa-129">Name</span><span class="sxs-lookup"><span data-stu-id="21aaa-129">Name</span></span>|<span data-ttu-id="21aaa-130">{2&gt;Value&lt;2}</span><span class="sxs-lookup"><span data-stu-id="21aaa-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="21aaa-131">Нет</span><span class="sxs-lookup"><span data-stu-id="21aaa-131">None</span></span>|<span data-ttu-id="21aaa-132">0</span><span class="sxs-lookup"><span data-stu-id="21aaa-132">0</span></span>|  
|<span data-ttu-id="21aaa-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="21aaa-133">SHA-1</span></span>|<span data-ttu-id="21aaa-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="21aaa-134">0x8004</span></span>|  
|<span data-ttu-id="21aaa-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="21aaa-135">SHA-256</span></span>|<span data-ttu-id="21aaa-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="21aaa-136">0x800c</span></span>|  
|<span data-ttu-id="21aaa-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="21aaa-137">SHA-384</span></span>|<span data-ttu-id="21aaa-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="21aaa-138">0x800d</span></span>|  
|<span data-ttu-id="21aaa-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="21aaa-139">SHA-512</span></span>|<span data-ttu-id="21aaa-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="21aaa-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="21aaa-141">Требования</span><span class="sxs-lookup"><span data-stu-id="21aaa-141">Requirements</span></span>  
 <span data-ttu-id="21aaa-142">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21aaa-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21aaa-143">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="21aaa-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="21aaa-144">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="21aaa-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21aaa-145">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21aaa-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21aaa-146">См. также:</span><span class="sxs-lookup"><span data-stu-id="21aaa-146">See also</span></span>

- [<span data-ttu-id="21aaa-147">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="21aaa-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="21aaa-148">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="21aaa-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="21aaa-149">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="21aaa-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="21aaa-150">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="21aaa-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
