---
title: "Метод ICLRStrongName::StrongNameSignatureGeneration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGeneration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 739dc0b08955b774f7fa15c3c346ec889f717dd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="62121-102">Метод ICLRStrongName::StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="62121-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="62121-103">Создает подпись со строгим именем для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="62121-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62121-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62121-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62121-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="62121-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="62121-106">[in] Путь к файлу, содержащему манифест сборки, для которого будет создаваться подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="62121-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="62121-107">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="62121-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="62121-108">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="62121-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="62121-109">В этом случае для подписания файла используется пара ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="62121-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="62121-110">Если `pbKeyBlob` не равно null, предполагается пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="62121-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="62121-111">Ключи должны быть 1024-разрядный Rivest шифрования RSA--Adleman () ключей подписывания.</span><span class="sxs-lookup"><span data-stu-id="62121-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="62121-112">Другие типы ключей не поддерживаются в данный момент.</span><span class="sxs-lookup"><span data-stu-id="62121-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="62121-113">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="62121-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="62121-114">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="62121-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="62121-115">Если `pbKeyBlob` равен null, контейнер ключей, заданные `wszKeyContainer` должна содержать пары ключей.</span><span class="sxs-lookup"><span data-stu-id="62121-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="62121-116">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="62121-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="62121-117">[out] Указатель на расположение, к которому Общеязыковая среда выполнения возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="62121-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="62121-118">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, заданный параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="62121-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="62121-119">Если `ppbSignatureBlob` — не null, общеязыковая среда выполнения выделяет место для возвращения подписи.</span><span class="sxs-lookup"><span data-stu-id="62121-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="62121-120">Вызывающий объект должен освободить это пространство с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="62121-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="62121-121">[out] Размер в байтах, возвращаемой подписи.</span><span class="sxs-lookup"><span data-stu-id="62121-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62121-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="62121-122">Return Value</span></span>  
 <span data-ttu-id="62121-123">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="62121-123">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62121-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="62121-124">Remarks</span></span>  
 <span data-ttu-id="62121-125">Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="62121-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="62121-126">Подпись может быть храниться непосредственно в файле или возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="62121-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62121-127">Требования</span><span class="sxs-lookup"><span data-stu-id="62121-127">Requirements</span></span>  
 <span data-ttu-id="62121-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62121-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62121-129">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="62121-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="62121-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62121-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62121-131">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62121-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62121-132">См. также</span><span class="sxs-lookup"><span data-stu-id="62121-132">See Also</span></span>  
 [<span data-ttu-id="62121-133">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="62121-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [<span data-ttu-id="62121-134">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="62121-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
