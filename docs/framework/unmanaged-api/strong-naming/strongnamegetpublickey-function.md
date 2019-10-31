---
title: Функция StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: 966a2a628f30f1999688da7b6ba435c1d6cb830c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73094667"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="5f862-102">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="5f862-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="5f862-103">Получает открытый ключ из пары закрытого и открытого ключей.</span><span class="sxs-lookup"><span data-stu-id="5f862-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="5f862-104">Пара ключей может быть задана как имя контейнера ключей в поставщике служб шифрования (CSP) или как необработанная коллекция байтов.</span><span class="sxs-lookup"><span data-stu-id="5f862-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="5f862-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="5f862-105">This function has been deprecated.</span></span> <span data-ttu-id="5f862-106">Используйте вместо этого метод [метод iclrstrongname:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5f862-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f862-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f862-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f862-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f862-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="5f862-109">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="5f862-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="5f862-110">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в CSP.</span><span class="sxs-lookup"><span data-stu-id="5f862-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="5f862-111">В этом случае `StrongNameGetPublicKey` извлекает открытый ключ из пары ключей, хранящейся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="5f862-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="5f862-112">Если `pbKeyBlob` не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="5f862-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="5f862-113">Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA).</span><span class="sxs-lookup"><span data-stu-id="5f862-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="5f862-114">В настоящее время не поддерживаются никакие другие типы ключей.</span><span class="sxs-lookup"><span data-stu-id="5f862-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5f862-115">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="5f862-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5f862-116">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey`.</span><span class="sxs-lookup"><span data-stu-id="5f862-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5f862-117">Если `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром `szKeyContainer`, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="5f862-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5f862-118">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="5f862-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="5f862-119">заполняет Возвращенный большой двоичный объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="5f862-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="5f862-120">Параметр `ppbPublicKeyBlob` выделяется средой CLR и возвращается вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="5f862-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="5f862-121">Вызывающий объект должен освободить память с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="5f862-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="5f862-122">заполняет Размер возвращенного большого двоичного объекта открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="5f862-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f862-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5f862-123">Return Value</span></span>  
 <span data-ttu-id="5f862-124">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="5f862-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f862-125">Заметки</span><span class="sxs-lookup"><span data-stu-id="5f862-125">Remarks</span></span>  
 <span data-ttu-id="5f862-126">Открытый ключ содержится в структуре [публиккэйблоб](publickeyblob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="5f862-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="5f862-127">Если функция `StrongNameGetPublicKey` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="5f862-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f862-128">Требования</span><span class="sxs-lookup"><span data-stu-id="5f862-128">Requirements</span></span>  
 <span data-ttu-id="5f862-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f862-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f862-130">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5f862-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5f862-131">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5f862-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f862-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f862-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f862-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5f862-133">See also</span></span>

- [<span data-ttu-id="5f862-134">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="5f862-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="5f862-135">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="5f862-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="5f862-136">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5f862-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="5f862-137">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="5f862-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
