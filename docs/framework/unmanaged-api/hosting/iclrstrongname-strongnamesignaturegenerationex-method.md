---
title: Метод ICLRStrongName::StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81f1eb4236bab72caf4421342e1f54d6d2f32607
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839042"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="9908a-102">Метод ICLRStrongName::StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="9908a-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="9908a-103">Создает подпись строгого имени для указанной сборки, в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="9908a-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9908a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9908a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9908a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9908a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9908a-106">[in] Путь к файлу, содержащему манифест сборки, для которого требуется создать подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="9908a-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="9908a-107">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9908a-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="9908a-108">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="9908a-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="9908a-109">В этом случае для подписывания файла используется пара ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="9908a-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="9908a-110">Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="9908a-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="9908a-111">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="9908a-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="9908a-112">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="9908a-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="9908a-113">Если `pbKeyBlob` имеет значение null, контейнере ключей `wszKeyContainer` предполагается, что содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="9908a-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="9908a-114">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9908a-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="9908a-115">[out] Указатель на расположение, к которому среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="9908a-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="9908a-116">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, указанный параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="9908a-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="9908a-117">Если `ppbSignatureBlob` — не равно null, среда CLR выделяет место для возвращения подписи.</span><span class="sxs-lookup"><span data-stu-id="9908a-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="9908a-118">Вызывающий объект должен освободить это пространство с помощью [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9908a-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="9908a-119">[out] Размер в байтах, возвращаемой сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="9908a-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9908a-120">[in] Один или несколько из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="9908a-120">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="9908a-121">`SN_SIGN_ALL_FILES` (0x00000001) — повторно вычисляет все хэши для связанных модулей.</span><span class="sxs-lookup"><span data-stu-id="9908a-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="9908a-122">`SN_TEST_SIGN` (0x00000002) — пробное подписание сборки.</span><span class="sxs-lookup"><span data-stu-id="9908a-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9908a-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9908a-123">Return Value</span></span>  
 <span data-ttu-id="9908a-124">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="9908a-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9908a-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="9908a-125">Remarks</span></span>  
 <span data-ttu-id="9908a-126">Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="9908a-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="9908a-127">Подпись может быть либо непосредственно в файле или возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="9908a-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="9908a-128">Если `SN_SIGN_ALL_FILES` указан, но не включается открытого ключа (оба `pbKeyBlob` и `wszFilePath` имеют значение null), вычисляются хэш-коды для связанных модулей, но сборка не подписана заново.</span><span class="sxs-lookup"><span data-stu-id="9908a-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="9908a-129">Если `SN_TEST_SIGN` указан, заголовок среды CLR не изменяется, чтобы указать, что сборка подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="9908a-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9908a-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9908a-130">Requirements</span></span>  
 <span data-ttu-id="9908a-131">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9908a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9908a-132">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9908a-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9908a-133">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9908a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9908a-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9908a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9908a-135">См. также</span><span class="sxs-lookup"><span data-stu-id="9908a-135">See Also</span></span>  
 [<span data-ttu-id="9908a-136">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="9908a-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [<span data-ttu-id="9908a-137">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9908a-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
