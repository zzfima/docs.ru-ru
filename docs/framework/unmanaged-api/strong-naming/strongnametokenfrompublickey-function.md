---
title: Функция StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175061"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="a4926-102">Функция StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="a4926-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="a4926-103">Получает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="a4926-103">Gets a token representing a public key.</span></span> <span data-ttu-id="a4926-104">Сильный маркер имени — это укороченная форма клавиши общего пользования.</span><span class="sxs-lookup"><span data-stu-id="a4926-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="a4926-105">Эта функция была амортизирована.</span><span class="sxs-lookup"><span data-stu-id="a4926-105">This function has been deprecated.</span></span> <span data-ttu-id="a4926-106">Вместо этого используйте метод [ICLRStrongName::StrongNameTokenFromPublicKey.](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)</span><span class="sxs-lookup"><span data-stu-id="a4926-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4926-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a4926-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4926-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="a4926-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="a4926-109">(в) Структура типа [PublicKeyBlob,](publickeyblob-structure.md) содержащая публичную часть ключевой пары, используемой для создания сильной подписи имен.</span><span class="sxs-lookup"><span data-stu-id="a4926-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="a4926-110">(в) Размер, в байтах, из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a4926-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="a4926-111">(ваут) Сильное имя маркер, соответствующий `pbPublicKeyBlob`ключу прошло в .</span><span class="sxs-lookup"><span data-stu-id="a4926-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="a4926-112">Общее время выполнения языка выделяет память, в которой возвращается токен.</span><span class="sxs-lookup"><span data-stu-id="a4926-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="a4926-113">Звонящее должно освободить эту память с помощью функции [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)</span><span class="sxs-lookup"><span data-stu-id="a4926-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="a4926-114">(ваут) Размер, в байтах, возвращенного сильного маркера имени.</span><span class="sxs-lookup"><span data-stu-id="a4926-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a4926-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a4926-115">Return Value</span></span>  
 <span data-ttu-id="a4926-116">`true`при успешном завершении; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="a4926-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4926-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="a4926-117">Remarks</span></span>  
 <span data-ttu-id="a4926-118">Сильный маркер имени — это укороченная форма общедоступного ключа, используемого для экономии места при хранении ключевой информации в метаданных.</span><span class="sxs-lookup"><span data-stu-id="a4926-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="a4926-119">В частности, сильные маркеры имен используются в ссылках на сборку для обозначения зависимой сборки.</span><span class="sxs-lookup"><span data-stu-id="a4926-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="a4926-120">Если `StrongNameTokenFromPublicKey` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.</span><span class="sxs-lookup"><span data-stu-id="a4926-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4926-121">Требования</span><span class="sxs-lookup"><span data-stu-id="a4926-121">Requirements</span></span>  
 <span data-ttu-id="a4926-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4926-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4926-123">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a4926-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a4926-124">**Библиотека:** Включено в качестве ресурса в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a4926-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="a4926-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4926-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4926-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a4926-126">See also</span></span>

- [<span data-ttu-id="a4926-127">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="a4926-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="a4926-128">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="a4926-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="a4926-129">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="a4926-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
