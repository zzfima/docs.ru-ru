---
title: "Функция StrongNameSignatureGeneration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureGeneration
helpviewer_keywords: StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c26e230f2bc0b115d898a34742fe3e637f934fd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="9c195-102">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="9c195-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="9c195-103">Создает подпись со строгим именем для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="9c195-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="9c195-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="9c195-104">This function has been deprecated.</span></span> <span data-ttu-id="9c195-105">Используйте [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="9c195-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c195-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c195-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c195-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c195-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9c195-108">[in] Путь к файлу, содержащему манифест сборки, для которого будет создаваться подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="9c195-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="9c195-109">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9c195-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="9c195-110">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="9c195-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="9c195-111">В этом случае для подписания файла используется пара ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="9c195-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="9c195-112">Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="9c195-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="9c195-113">Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания.</span><span class="sxs-lookup"><span data-stu-id="9c195-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="9c195-114">Другие типы ключей не поддерживаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="9c195-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9c195-115">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9c195-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9c195-116">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="9c195-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9c195-117">Если `pbKeyBlob` равен null, контейнер ключей, заданные `wszKeyContainer` должна содержать пары ключей.</span><span class="sxs-lookup"><span data-stu-id="9c195-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9c195-118">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9c195-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="9c195-119">[out] Указатель на расположение, к которому Общеязыковая среда выполнения возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="9c195-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="9c195-120">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, заданный параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="9c195-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="9c195-121">Если `ppbSignatureBlob` — не null, общеязыковая среда выполнения выделяет место для возвращения подписи.</span><span class="sxs-lookup"><span data-stu-id="9c195-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="9c195-122">Вызывающий объект должен освободить это место с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="9c195-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="9c195-123">[out] Размер в байтах, возвращаемой подписи.</span><span class="sxs-lookup"><span data-stu-id="9c195-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c195-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c195-124">Return Value</span></span>  
 <span data-ttu-id="9c195-125">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9c195-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c195-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c195-126">Remarks</span></span>  
 <span data-ttu-id="9c195-127">Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="9c195-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="9c195-128">Подпись может быть храниться непосредственно в файле или возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="9c195-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="9c195-129">Если `StrongNameSignatureGeneration` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="9c195-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c195-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9c195-130">Requirements</span></span>  
 <span data-ttu-id="9c195-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c195-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c195-132">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9c195-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9c195-133">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c195-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c195-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c195-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c195-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9c195-135">See Also</span></span>  
 [<span data-ttu-id="9c195-136">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="9c195-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="9c195-137">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="9c195-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="9c195-138">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9c195-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
