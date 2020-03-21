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
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176933"
---
# <a name="strongnamegetpublickey-function"></a><span data-ttu-id="7bd8d-102">Функция StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="7bd8d-102">StrongNameGetPublicKey Function</span></span>
<span data-ttu-id="7bd8d-103">Получает открытый ключ из пары закрытого и открытого ключей.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-103">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="7bd8d-104">Ключевая пара может поставляться либо в качестве ключевого имени контейнера в рамках криптографического поставщика услуг (CSP), либо в виде сырой коллекции байтов.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
 <span data-ttu-id="7bd8d-105">Эта функция была амортизирована.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-105">This function has been deprecated.</span></span> <span data-ttu-id="7bd8d-106">Вместо этого используйте метод [ICLRStrongName::StrongNameGetPublicKey.](../hosting/iclrstrongname-strongnamegetpublickey-method.md)</span><span class="sxs-lookup"><span data-stu-id="7bd8d-106">Use the [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd8d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7bd8d-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bd8d-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="7bd8d-108">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="7bd8d-109">(в) Название ключевого контейнера, содержащего публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-109">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="7bd8d-110">Если `pbKeyBlob` он `szKeyContainer` недействителен, необходимо указать действительный контейнер в рамках CSP.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-110">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="7bd8d-111">В этом `StrongNameGetPublicKey` случае извлекает открытый ключ из пары ключей, хранящейся в контейнере.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-111">In this case, `StrongNameGetPublicKey` extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="7bd8d-112">Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).</span><span class="sxs-lookup"><span data-stu-id="7bd8d-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="7bd8d-113">Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="7bd8d-114">В настоящее время никакие другие типы ключей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="7bd8d-115">(в) Указатель на публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="7bd8d-116">Эта пара находится в формате, `CryptExportKey` созданном функцией Win32.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="7bd8d-117">Если `pbKeyBlob` он недействителен, `szKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-117">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="7bd8d-118">(в) Размер, в байтах, из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="7bd8d-119">(ваут) Вернулся общественный ключ BLOB.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-119">[out] The returned public key BLOB.</span></span> <span data-ttu-id="7bd8d-120">Параметр `ppbPublicKeyBlob` выделяется общим временем выполнения языка и возвращается вызывающему.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-120">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="7bd8d-121">Звонящее должно освободить память с помощью функции [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)</span><span class="sxs-lookup"><span data-stu-id="7bd8d-121">The caller must free the memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="7bd8d-122">(ваут) Размер возвращенного публичного ключа BLOB.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-122">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7bd8d-123">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7bd8d-123">Return Value</span></span>  
 <span data-ttu-id="7bd8d-124">`true`при успешном завершении; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="7bd8d-124">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bd8d-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="7bd8d-125">Remarks</span></span>  
 <span data-ttu-id="7bd8d-126">Открытый ключ содержится в структуре [PublicKeyBlob.](publickeyblob-structure.md)</span><span class="sxs-lookup"><span data-stu-id="7bd8d-126">The public key is contained in a [PublicKeyBlob](publickeyblob-structure.md) structure.</span></span>  
  
 <span data-ttu-id="7bd8d-127">Если `StrongNameGetPublicKey` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.</span><span class="sxs-lookup"><span data-stu-id="7bd8d-127">If the `StrongNameGetPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bd8d-128">Требования</span><span class="sxs-lookup"><span data-stu-id="7bd8d-128">Requirements</span></span>  
 <span data-ttu-id="7bd8d-129">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bd8d-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd8d-130">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7bd8d-130">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7bd8d-131">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7bd8d-131">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bd8d-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd8d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd8d-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7bd8d-133">See also</span></span>

- [<span data-ttu-id="7bd8d-134">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="7bd8d-134">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="7bd8d-135">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="7bd8d-135">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="7bd8d-136">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7bd8d-136">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="7bd8d-137">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="7bd8d-137">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
