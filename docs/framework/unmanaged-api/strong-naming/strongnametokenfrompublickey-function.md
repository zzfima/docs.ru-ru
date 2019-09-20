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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 197504cbb0dd66c0cf43dee718026fc63e918d60
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798852"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="83a55-102">Функция StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="83a55-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="83a55-103">Получает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="83a55-103">Gets a token representing a public key.</span></span> <span data-ttu-id="83a55-104">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="83a55-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="83a55-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="83a55-105">This function has been deprecated.</span></span> <span data-ttu-id="83a55-106">Используйте вместо этого метод [метод iclrstrongname:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .</span><span class="sxs-lookup"><span data-stu-id="83a55-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83a55-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83a55-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83a55-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="83a55-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="83a55-109">окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="83a55-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="83a55-110">окне Размер (в байтах `pbPublicKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="83a55-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="83a55-111">заполняет Маркер строгого имени, соответствующий переданному `pbPublicKeyBlob`ключу.</span><span class="sxs-lookup"><span data-stu-id="83a55-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="83a55-112">Среда CLR выделяет память, в которую возвращается маркер.</span><span class="sxs-lookup"><span data-stu-id="83a55-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="83a55-113">Вызывающий объект должен освободить эту память с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .</span><span class="sxs-lookup"><span data-stu-id="83a55-113">The caller must free this memory by using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="83a55-114">заполняет Размер возвращенного маркера строгого имени в байтах.</span><span class="sxs-lookup"><span data-stu-id="83a55-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83a55-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83a55-115">Return Value</span></span>  
 <span data-ttu-id="83a55-116">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="83a55-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83a55-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="83a55-117">Remarks</span></span>  
 <span data-ttu-id="83a55-118">Маркер строгого имени — это сокращенная форма открытого ключа, используемая для экономии места при хранении ключевых сведений в метаданных.</span><span class="sxs-lookup"><span data-stu-id="83a55-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="83a55-119">В частности, маркеры строгого имени используются в ссылках на сборки для ссылки на зависимую сборку.</span><span class="sxs-lookup"><span data-stu-id="83a55-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="83a55-120">Если функция `StrongNameTokenFromPublicKey` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="83a55-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83a55-121">Требования</span><span class="sxs-lookup"><span data-stu-id="83a55-121">Requirements</span></span>  
 <span data-ttu-id="83a55-122">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83a55-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83a55-123">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="83a55-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="83a55-124">**Библиотечная** Включается в качестве ресурса в библиотеку Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="83a55-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="83a55-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83a55-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a55-126">См. также</span><span class="sxs-lookup"><span data-stu-id="83a55-126">See also</span></span>

- [<span data-ttu-id="83a55-127">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="83a55-127">StrongNameTokenFromPublicKey Method</span></span>](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="83a55-128">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="83a55-128">StrongNameGetPublicKey Method</span></span>](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="83a55-129">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="83a55-129">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)
