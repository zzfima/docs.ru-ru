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
ms.openlocfilehash: 48cdd550e5d8c7c75a603d74456e99a066d5c599
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798976"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="e3ae7-102">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="e3ae7-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="e3ae7-103">Создает подпись строгого имени для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="e3ae7-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-104">This function has been deprecated.</span></span> <span data-ttu-id="e3ae7-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e3ae7-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ae7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3ae7-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3ae7-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3ae7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e3ae7-108">окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="e3ae7-109">окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="e3ae7-110">Если `pbKeyBlob` параметр имеет значение `wszKeyContainer` null, необходимо указать допустимый контейнер в поставщике служб шифрования (CSP).</span><span class="sxs-lookup"><span data-stu-id="e3ae7-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="e3ae7-111">В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="e3ae7-112">Если `pbKeyBlob` значение не равно null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).</span><span class="sxs-lookup"><span data-stu-id="e3ae7-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="e3ae7-113">Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA).</span><span class="sxs-lookup"><span data-stu-id="e3ae7-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="e3ae7-114">В настоящее время не поддерживаются никакие другие типы ключей.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e3ae7-115">окне Указатель на пару открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e3ae7-116">Эта пара имеет формат, созданный функцией Win32 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="e3ae7-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e3ae7-117">Если `pbKeyBlob` аргумент имеет значение null, предполагается, `wszKeyContainer` что контейнер ключей, заданный параметром, содержит пару ключей.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e3ae7-118">окне Размер (в байтах `pbKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="e3ae7-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="e3ae7-119">заполняет Указатель на расположение, в которое среда CLR возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="e3ae7-120">Если `ppbSignatureBlob` параметр имеет значение null, среда выполнения сохраняет подпись в файле, указанном параметром `wszFilePath`.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="e3ae7-121">Если `ppbSignatureBlob` значение не равно null, среда CLR выделяет пространство, в которое возвращается подпись.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="e3ae7-122">Вызывающий объект должен освободить это пространство с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="e3ae7-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="e3ae7-123">заполняет Размер возвращенной сигнатуры в байтах.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3ae7-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3ae7-124">Return Value</span></span>  
 <span data-ttu-id="e3ae7-125">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="e3ae7-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3ae7-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="e3ae7-126">Remarks</span></span>  
 <span data-ttu-id="e3ae7-127">Укажите значение NULL `wszFilePath` для, чтобы вычислить размер подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="e3ae7-128">Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="e3ae7-129">Если функция `StrongNameSignatureGeneration` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="e3ae7-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3ae7-130">Требования</span><span class="sxs-lookup"><span data-stu-id="e3ae7-130">Requirements</span></span>  
 <span data-ttu-id="e3ae7-131">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ae7-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3ae7-132">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="e3ae7-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e3ae7-133">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e3ae7-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e3ae7-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3ae7-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ae7-135">См. также</span><span class="sxs-lookup"><span data-stu-id="e3ae7-135">See also</span></span>

- [<span data-ttu-id="e3ae7-136">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="e3ae7-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="e3ae7-137">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="e3ae7-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="e3ae7-138">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e3ae7-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
