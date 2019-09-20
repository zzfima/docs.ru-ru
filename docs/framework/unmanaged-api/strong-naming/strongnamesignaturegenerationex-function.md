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
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798985"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="bcab1-102">Функция StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="bcab1-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="bcab1-103">Создает подпись строгого имени для указанной сборки в соответствии с заданными флагами.</span><span class="sxs-lookup"><span data-stu-id="bcab1-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="bcab1-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="bcab1-104">This function has been deprecated.</span></span> <span data-ttu-id="bcab1-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bcab1-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcab1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcab1-106">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="bcab1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcab1-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bcab1-108">окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="bcab1-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="bcab1-109">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="bcab1-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="bcab1-110">Если `pbKeyBlob` параметр имеет значение `wszKeyContainer` null, необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="bcab1-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="bcab1-111">В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="bcab1-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="bcab1-112">Если `pbKeyBlob` значение не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="bcab1-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="bcab1-113">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="bcab1-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="bcab1-114">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="bcab1-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="bcab1-115">Если `pbKeyBlob` аргумент имеет значение null, предполагается, `wszKeyContainer` что контейнер ключей, заданный параметром, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="bcab1-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="bcab1-116">окне Размер (в байтах `pbKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="bcab1-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="bcab1-117">заполняет Указатель на расположение, в которое среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="bcab1-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="bcab1-118">Если `ppbSignatureBlob` параметр имеет значение null, среда выполнения сохраняет подпись в файле, указанном параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="bcab1-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="bcab1-119">Если `ppbSignatureBlob` значение не равно null, среда CLR выделяет пространство, в которое возвращается подпись.</span><span class="sxs-lookup"><span data-stu-id="bcab1-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="bcab1-120">Вызывающий объект должен освободить это пространство с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="bcab1-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="bcab1-121">заполняет Размер возвращенной сигнатуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="bcab1-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="bcab1-122">окне Одно или несколько из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="bcab1-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="bcab1-123">`SN_SIGN_ALL_FILES`(0x00000001) — повторное вычисление всех хэшей для связанных модулей.</span><span class="sxs-lookup"><span data-stu-id="bcab1-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="bcab1-124">`SN_TEST_SIGN`(0x00000002) — Тестовая подпись сборки.</span><span class="sxs-lookup"><span data-stu-id="bcab1-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcab1-125">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcab1-125">Return Value</span></span>  
 <span data-ttu-id="bcab1-126">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="bcab1-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcab1-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcab1-127">Remarks</span></span>  
 <span data-ttu-id="bcab1-128">Укажите значение NULL `wszFilePath` для, чтобы вычислить размер подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="bcab1-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="bcab1-129">Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="bcab1-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="bcab1-130">Если `SN_SIGN_ALL_FILES` указан параметр, но открытый ключ не включен `pbKeyBlob` (и `wszFilePath` имеет значение null), хэши для связанных модулей пересчитываются, но сборка не подписывается повторно.</span><span class="sxs-lookup"><span data-stu-id="bcab1-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="bcab1-131">Если `SN_TEST_SIGN` указан параметр, заголовок среды CLR не изменяется, чтобы указать, что сборка подписана строгим именем.</span><span class="sxs-lookup"><span data-stu-id="bcab1-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="bcab1-132">Если функция `StrongNameSignatureGenerationEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="bcab1-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcab1-133">Требования</span><span class="sxs-lookup"><span data-stu-id="bcab1-133">Requirements</span></span>  
 <span data-ttu-id="bcab1-134">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcab1-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcab1-135">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="bcab1-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bcab1-136">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bcab1-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bcab1-137">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcab1-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcab1-138">См. также</span><span class="sxs-lookup"><span data-stu-id="bcab1-138">See also</span></span>

- [<span data-ttu-id="bcab1-139">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="bcab1-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="bcab1-140">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="bcab1-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="bcab1-141">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="bcab1-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
