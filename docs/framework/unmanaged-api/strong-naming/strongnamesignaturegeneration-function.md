---
title: Функция StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e7df65c28fad6fa79ec7a18d8511955330b2817
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227747"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="d6af7-102">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="d6af7-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="d6af7-103">Создает подпись строгого имени для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="d6af7-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="d6af7-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="d6af7-104">This function has been deprecated.</span></span> <span data-ttu-id="d6af7-105">Используйте [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="d6af7-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6af7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d6af7-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d6af7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d6af7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d6af7-108">[in] Путь к файлу, содержащему манифест сборки, для которого требуется создать подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="d6af7-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="d6af7-109">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="d6af7-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="d6af7-110">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="d6af7-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="d6af7-111">В этом случае для подписывания файла используется пара ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="d6af7-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="d6af7-112">Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="d6af7-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="d6af7-113">Ключи должны быть Rivest-Шамир-Adleman 1024-разрядный (RSA) ключи подписывания.</span><span class="sxs-lookup"><span data-stu-id="d6af7-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="d6af7-114">Другие типы ключей не поддерживаются в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="d6af7-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d6af7-115">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="d6af7-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d6af7-116">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="d6af7-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d6af7-117">Если `pbKeyBlob` имеет значение null, контейнере ключей `wszKeyContainer` предполагается, что содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="d6af7-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d6af7-118">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d6af7-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="d6af7-119">[out] Указатель на расположение, к которому среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="d6af7-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="d6af7-120">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, указанный параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="d6af7-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="d6af7-121">Если `ppbSignatureBlob` — не равно null, среда CLR выделяет место для возвращения подписи.</span><span class="sxs-lookup"><span data-stu-id="d6af7-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="d6af7-122">Вызывающий объект должен освободить это пространство с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="d6af7-122">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="d6af7-123">[out] Размер в байтах, возвращаемой сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="d6af7-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6af7-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d6af7-124">Return Value</span></span>  
 `true` <span data-ttu-id="d6af7-125">После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="d6af7-125">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6af7-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d6af7-126">Remarks</span></span>  
 <span data-ttu-id="d6af7-127">Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="d6af7-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="d6af7-128">Подписи могут быть сохранены либо непосредственно в файле или возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="d6af7-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="d6af7-129">Если `StrongNameSignatureGeneration` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="d6af7-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6af7-130">Требования</span><span class="sxs-lookup"><span data-stu-id="d6af7-130">Requirements</span></span>  
 <span data-ttu-id="d6af7-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6af7-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6af7-132">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d6af7-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d6af7-133">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6af7-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d6af7-134">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d6af7-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d6af7-135">См. также</span><span class="sxs-lookup"><span data-stu-id="d6af7-135">See also</span></span>

- [<span data-ttu-id="d6af7-136">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="d6af7-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="d6af7-137">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="d6af7-137">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="d6af7-138">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d6af7-138">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
