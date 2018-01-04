---
title: "Функция StrongNameGetPublicKey"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameGetPublicKey
helpviewer_keywords: StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cec7c1edac24d43924abb2bf8784d45ed6372129
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="a7c7f-102">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a7c7f-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="a7c7f-103">Возвращает открытый ключ из пары закрытого и открытого ключей.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="a7c7f-104">Пара ключей может предоставляться в виде имени контейнера ключей в поставщике служб шифрования (CSP) или как коллекция необработанных байтов.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="a7c7f-105">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-105">This function has been deprecated.</span></span> <span data-ttu-id="a7c7f-106">Используйте [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7c7f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7c7f-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7c7f-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7c7f-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="a7c7f-109">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="a7c7f-110">Если `pbKeyBlob` имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб Шифрования.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="a7c7f-111">В этом случае `StrongNameGetPublicKey` извлекает открытый ключ из пары ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="a7c7f-112">Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="a7c7f-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a7c7f-113">Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a7c7f-114">Другие типы ключей не поддерживаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a7c7f-115">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a7c7f-116">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a7c7f-117">Если `pbKeyBlob` равен null, контейнер ключей, заданные `szKeyContainer` должна содержать пары ключей.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a7c7f-118">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="a7c7f-119">[out] Возвращаемый открытый ключ большого двоичного ОБЪЕКТА.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="a7c7f-120">`ppbPublicKeyBlob` Параметра выделяется средой CLR и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="a7c7f-121">Вызывающий объект должен освободить память с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-121">The caller must free the memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="a7c7f-122">[out] Размер возвращаемого BLOB-объект открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7c7f-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7c7f-123">Return Value</span></span>  
 <span data-ttu-id="a7c7f-124">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7c7f-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7c7f-125">Remarks</span></span>  
 <span data-ttu-id="a7c7f-126">Открытый ключ содержится в [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="a7c7f-127">Если `StrongNameGetPublicKey` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="a7c7f-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7c7f-128">Требования</span><span class="sxs-lookup"><span data-stu-id="a7c7f-128">Requirements</span></span>  
 <span data-ttu-id="a7c7f-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7c7f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7c7f-130">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a7c7f-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a7c7f-131">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7c7f-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a7c7f-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7c7f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7c7f-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a7c7f-133">See Also</span></span>  
 [<span data-ttu-id="a7c7f-134">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a7c7f-134">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="a7c7f-135">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="a7c7f-135">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="a7c7f-136">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a7c7f-136">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [<span data-ttu-id="a7c7f-137">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="a7c7f-137">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
