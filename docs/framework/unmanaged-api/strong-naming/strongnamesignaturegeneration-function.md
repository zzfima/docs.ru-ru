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
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176907"
---
# <a name="strongnamesignaturegeneration-function"></a><span data-ttu-id="0b92c-102">Функция StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="0b92c-102">StrongNameSignatureGeneration Function</span></span>
<span data-ttu-id="0b92c-103">Создает подпись строгого имени для указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="0b92c-103">Generates a strong name signature for the specified assembly.</span></span>  
  
 <span data-ttu-id="0b92c-104">Эта функция была амортизирована.</span><span class="sxs-lookup"><span data-stu-id="0b92c-104">This function has been deprecated.</span></span> <span data-ttu-id="0b92c-105">Вместо этого используйте метод [ICLRStrongName::StrongNameSignatureGeneration.](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)</span><span class="sxs-lookup"><span data-stu-id="0b92c-105">Use the [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b92c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b92c-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0b92c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b92c-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0b92c-108">(в) Путь к файлу, содержащий манифест сборки, для которого будет создана сильная подпись имени.</span><span class="sxs-lookup"><span data-stu-id="0b92c-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="0b92c-109">(в) Название ключевого контейнера, содержащего публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="0b92c-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="0b92c-110">Если `pbKeyBlob` он `wszKeyContainer` недействителен, необходимо указать действительный контейнер в рамках поставщика криптографических услуг (CSP).</span><span class="sxs-lookup"><span data-stu-id="0b92c-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="0b92c-111">В этом случае пара ключей, хранящаяся в контейнере, используется для подписания файла.</span><span class="sxs-lookup"><span data-stu-id="0b92c-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="0b92c-112">Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).</span><span class="sxs-lookup"><span data-stu-id="0b92c-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="0b92c-113">Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей.</span><span class="sxs-lookup"><span data-stu-id="0b92c-113">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="0b92c-114">В настоящее время никакие другие типы ключей не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0b92c-114">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="0b92c-115">(в) Указатель на публичную/частную ключевую пару.</span><span class="sxs-lookup"><span data-stu-id="0b92c-115">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="0b92c-116">Эта пара находится в формате, `CryptExportKey` созданном функцией Win32.</span><span class="sxs-lookup"><span data-stu-id="0b92c-116">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="0b92c-117">Если `pbKeyBlob` он недействителен, `wszKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.</span><span class="sxs-lookup"><span data-stu-id="0b92c-117">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="0b92c-118">(в) Размер, в байтах, из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0b92c-118">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="0b92c-119">(ваут) Указатель на место, к которому общее время выполнения языка возвращает подпись.</span><span class="sxs-lookup"><span data-stu-id="0b92c-119">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="0b92c-120">Если `ppbSignatureBlob` время выполнения является нулевым, время выполнения `wszFilePath`хранит подпись в файле, указанном .</span><span class="sxs-lookup"><span data-stu-id="0b92c-120">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="0b92c-121">Если `ppbSignatureBlob` время выполнения общего языка не является нулевым, то время выполнения общего языка выделяет пространство для возврата подписи.</span><span class="sxs-lookup"><span data-stu-id="0b92c-121">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="0b92c-122">Абонент должен освободить это пространство, используя функцию [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)</span><span class="sxs-lookup"><span data-stu-id="0b92c-122">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="0b92c-123">(ваут) Размер, в байтах, возвращенной подписи.</span><span class="sxs-lookup"><span data-stu-id="0b92c-123">[out] The size, in bytes, of the returned signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b92c-124">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0b92c-124">Return Value</span></span>  
 <span data-ttu-id="0b92c-125">`true`при успешном завершении; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="0b92c-125">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b92c-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b92c-126">Remarks</span></span>  
 <span data-ttu-id="0b92c-127">Укажите `wszFilePath` нулевую для расчета размера подписи без создания подписи.</span><span class="sxs-lookup"><span data-stu-id="0b92c-127">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="0b92c-128">Подпись может храниться либо непосредственно в файле, либо возвращена вызывающему.</span><span class="sxs-lookup"><span data-stu-id="0b92c-128">The signature can be stored either directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="0b92c-129">Если `StrongNameSignatureGeneration` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.</span><span class="sxs-lookup"><span data-stu-id="0b92c-129">If the `StrongNameSignatureGeneration` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b92c-130">Требования</span><span class="sxs-lookup"><span data-stu-id="0b92c-130">Requirements</span></span>  
 <span data-ttu-id="0b92c-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b92c-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b92c-132">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0b92c-132">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0b92c-133">**Библиотека:** Включено в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b92c-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b92c-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b92c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b92c-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b92c-135">See also</span></span>

- [<span data-ttu-id="0b92c-136">Метод StrongNameSignatureGeneration</span><span class="sxs-lookup"><span data-stu-id="0b92c-136">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="0b92c-137">Метод StrongNameSignatureGenerationEx</span><span class="sxs-lookup"><span data-stu-id="0b92c-137">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="0b92c-138">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0b92c-138">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
