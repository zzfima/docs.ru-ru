---
title: Метод ICLRStrongName::StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 679afd7b1053043a7cc43304a544a516024a4696
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165789"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a><span data-ttu-id="734ac-102">Метод ICLRStrongName::StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="734ac-102">ICLRStrongName::StrongNameSignatureGeneration Method</span></span>
<span data-ttu-id="734ac-103">Создает подпись строгого имени для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="734ac-103">Generates a strong name signature for the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="734ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="734ac-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="734ac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="734ac-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="734ac-106">[in] Путь к файлу, содержащему манифест сборки, для которого требуется создать подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="734ac-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="734ac-107">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="734ac-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="734ac-108">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="734ac-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="734ac-109">В этом случае для подписывания файла используется пара ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="734ac-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="734ac-110">Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="734ac-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="734ac-111">Ключи должны быть Rivest-Шамир-Adleman 1024-разрядный (RSA) ключи подписывания.</span><span class="sxs-lookup"><span data-stu-id="734ac-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="734ac-112">Другие типы ключей не поддерживаются в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="734ac-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="734ac-113">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="734ac-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="734ac-114">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="734ac-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="734ac-115">Если `pbKeyBlob` имеет значение null, контейнере ключей `wszKeyContainer` предполагается, что содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="734ac-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="734ac-116">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="734ac-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="734ac-117">[out] Указатель на расположение, к которому среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="734ac-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="734ac-118">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, указанный параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="734ac-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="734ac-119">Если `ppbSignatureBlob` — не равно null, среда CLR выделяет место для возвращения подписи.</span><span class="sxs-lookup"><span data-stu-id="734ac-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="734ac-120">Вызывающий объект должен освободить это пространство с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="734ac-120">The caller must free this space by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="734ac-121">[out] Размер в байтах, возвращаемой сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="734ac-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="734ac-122">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="734ac-122">Return Value</span></span>  
 `S_OK` <span data-ttu-id="734ac-123">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="734ac-123">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="734ac-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="734ac-124">Remarks</span></span>  
 <span data-ttu-id="734ac-125">Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="734ac-125">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="734ac-126">Подписи могут быть сохранены либо непосредственно в файле или возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="734ac-126">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="734ac-127">Требования</span><span class="sxs-lookup"><span data-stu-id="734ac-127">Requirements</span></span>  
 <span data-ttu-id="734ac-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="734ac-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="734ac-129">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="734ac-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="734ac-130">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="734ac-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="734ac-131">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="734ac-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="734ac-132">См. также</span><span class="sxs-lookup"><span data-stu-id="734ac-132">See also</span></span>

- [<span data-ttu-id="734ac-133">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="734ac-133">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="734ac-134">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="734ac-134">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
