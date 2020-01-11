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
ms.openlocfilehash: fd7f95ea01de397509c2a7b5fc08c0ac401a8da9
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899609"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="9a502-102">Метод ICLRStrongName::StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="9a502-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="9a502-103">Возвращает открытый ключ из пары открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9a502-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="9a502-104">Пара ключей может быть задана как имя контейнера ключей в поставщике служб шифрования (CSP) или как необработанная коллекция байтов.</span><span class="sxs-lookup"><span data-stu-id="9a502-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a502-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a502-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a502-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a502-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="9a502-107">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9a502-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="9a502-108">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в CSP.</span><span class="sxs-lookup"><span data-stu-id="9a502-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="9a502-109">В этом случае метод [метод iclrstrongname:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) извлекает открытый ключ из пары ключей, хранящейся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="9a502-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="9a502-110">Если `pbKeyBlob` не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="9a502-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9a502-111">Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA).</span><span class="sxs-lookup"><span data-stu-id="9a502-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9a502-112">В настоящее время не поддерживаются никакие другие типы ключей.</span><span class="sxs-lookup"><span data-stu-id="9a502-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9a502-113">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9a502-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9a502-114">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="9a502-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9a502-115">Если `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром `szKeyContainer`, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="9a502-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9a502-116">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="9a502-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="9a502-117">заполняет Возвращенный большой двоичный объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9a502-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="9a502-118">Параметр `ppbPublicKeyBlob` выделяется средой CLR и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="9a502-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="9a502-119">Вызывающий объект должен освободить память с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9a502-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="9a502-120">заполняет Размер возвращенного большого двоичного объекта открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="9a502-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a502-121">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a502-121">Return Value</span></span>  
 <span data-ttu-id="9a502-122">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="9a502-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a502-123">Заметки</span><span class="sxs-lookup"><span data-stu-id="9a502-123">Remarks</span></span>  
 <span data-ttu-id="9a502-124">Открытый ключ содержится в структуре [публиккэйблоб](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="9a502-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a502-125">Требования</span><span class="sxs-lookup"><span data-stu-id="9a502-125">Requirements</span></span>  
 <span data-ttu-id="9a502-126">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a502-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a502-127">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="9a502-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9a502-128">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9a502-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a502-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a502-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a502-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="9a502-130">See also</span></span>

- [<span data-ttu-id="9a502-131">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="9a502-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="9a502-132">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="9a502-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="9a502-133">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9a502-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
