---
title: Функция StrongNameSignatureGenerationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c63a586473128281843ec100905e63d381f1a3f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500942"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="dc0c8-102">Функция StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="dc0c8-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="dc0c8-103">Создает подпись строгого имени для указанной сборки, в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="dc0c8-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-104">This function has been deprecated.</span></span> <span data-ttu-id="dc0c8-105">Используйте [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0c8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc0c8-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc0c8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="dc0c8-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="dc0c8-108">[in] Путь к файлу, содержащему манифест сборки, для которого требуется создать подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="dc0c8-109">[in] Имя контейнера ключа, который содержит пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="dc0c8-110">Если `pbKeyBlob` имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщик служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="dc0c8-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="dc0c8-111">В этом случае для подписывания файла используется пара ключей, хранящихся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="dc0c8-112">Если `pbKeyBlob` не равно null, предполагается, что пары ключей должен содержаться в ключевых большой двоичный объект (BLOB).</span><span class="sxs-lookup"><span data-stu-id="dc0c8-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="dc0c8-113">[in] Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="dc0c8-114">Эта пара имеет формат, созданные Win32 `CryptExportKey` функции.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="dc0c8-115">Если `pbKeyBlob` имеет значение null, контейнере ключей `wszKeyContainer` предполагается, что содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="dc0c8-116">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="dc0c8-117">[out] Указатель на расположение, к которому среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="dc0c8-118">Если `ppbSignatureBlob` имеет значение null, среда выполнения сохраняет подпись в файл, указанный параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="dc0c8-119">Если `ppbSignatureBlob` — не равно null, среда CLR выделяет место для возвращения подписи.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="dc0c8-120">Вызывающий объект должен освободить это пространство с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-120">The caller must free this space using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="dc0c8-121">[out] Размер в байтах, возвращаемой сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dc0c8-122">[in] Один или несколько из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="dc0c8-122">[in] One or more of the following values:</span></span>  
  
-   <span data-ttu-id="dc0c8-123">`SN_SIGN_ALL_FILES` (0x00000001) — повторно вычисляет все хэши для связанных модулей.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
-   <span data-ttu-id="dc0c8-124">`SN_TEST_SIGN` (0x00000002) — пробное подписание сборки.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dc0c8-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="dc0c8-125">Return Value</span></span>  
 <span data-ttu-id="dc0c8-126">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc0c8-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc0c8-127">Remarks</span></span>  
 <span data-ttu-id="dc0c8-128">Укажите значение null для `wszFilePath` для вычисления размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="dc0c8-129">Подпись может быть либо непосредственно в файле или возвращается вызывающей стороне.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="dc0c8-130">Если `SN_SIGN_ALL_FILES` указан, но не включается открытого ключа (оба `pbKeyBlob` и `wszFilePath` имеют значение null), вычисляются хэш-коды для связанных модулей, но сборка не подписана заново.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="dc0c8-131">Если `SN_TEST_SIGN` указан, заголовок среды CLR не изменяется, чтобы указать, что сборка подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="dc0c8-132">Если `StrongNameSignatureGenerationEx` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="dc0c8-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc0c8-133">Требования</span><span class="sxs-lookup"><span data-stu-id="dc0c8-133">Requirements</span></span>  
 <span data-ttu-id="dc0c8-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc0c8-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc0c8-135">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="dc0c8-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="dc0c8-136">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc0c8-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc0c8-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc0c8-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0c8-138">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0c8-138">See also</span></span>
- [<span data-ttu-id="dc0c8-139">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="dc0c8-139">StrongNameSignatureGenerationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="dc0c8-140">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="dc0c8-140">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="dc0c8-141">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="dc0c8-141">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
