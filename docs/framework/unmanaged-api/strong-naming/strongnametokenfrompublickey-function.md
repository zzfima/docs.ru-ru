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
ms.openlocfilehash: 9a5c9336d571fb392fbed9fed2196fca813bc7d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674668"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="95814-102">Функция StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="95814-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="95814-103">Получает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="95814-103">Gets a token representing a public key.</span></span> <span data-ttu-id="95814-104">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="95814-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="95814-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="95814-105">This function has been deprecated.</span></span> <span data-ttu-id="95814-106">Используйте [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="95814-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95814-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95814-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95814-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="95814-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="95814-109">[in] Структура типа [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащий открытую часть пары ключей, использованного для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="95814-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="95814-110">[in] Размер в байтах из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="95814-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="95814-111">[out] Токен строгое имя, соответствующее ключу, переданный в `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="95814-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="95814-112">Среда CLR выделяет память, в котором для возврата токена.</span><span class="sxs-lookup"><span data-stu-id="95814-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="95814-113">Вызывающий объект должен освободить эту память с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="95814-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="95814-114">[out] Размер в байтах, возвращенный строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="95814-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95814-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="95814-115">Return Value</span></span>  
 <span data-ttu-id="95814-116">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="95814-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95814-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="95814-117">Remarks</span></span>  
 <span data-ttu-id="95814-118">Маркер строгого имени — это сокращенная форма открытого ключа, используемого для экономии места, при сохранении информации ключа в метаданных.</span><span class="sxs-lookup"><span data-stu-id="95814-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="95814-119">В частности маркеры строгого имени используются в ссылках сборок для ссылки на зависимые сборки.</span><span class="sxs-lookup"><span data-stu-id="95814-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="95814-120">Если `StrongNameTokenFromPublicKey` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="95814-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95814-121">Требования</span><span class="sxs-lookup"><span data-stu-id="95814-121">Requirements</span></span>  
 <span data-ttu-id="95814-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95814-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95814-123">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="95814-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="95814-124">**Библиотека:** Включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="95814-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="95814-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95814-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95814-126">См. также</span><span class="sxs-lookup"><span data-stu-id="95814-126">See also</span></span>
- [<span data-ttu-id="95814-127">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="95814-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="95814-128">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="95814-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="95814-129">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="95814-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
