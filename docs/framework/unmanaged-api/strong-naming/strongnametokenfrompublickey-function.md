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
ms.openlocfilehash: fbfd3ae32f4d3033894fdaf6b1bcc880c324e928
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219802"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="965da-102">Функция StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="965da-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="965da-103">Получает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="965da-103">Gets a token representing a public key.</span></span> <span data-ttu-id="965da-104">Маркер строгого имени — это сокращенная форма открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="965da-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="965da-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="965da-105">This function has been deprecated.</span></span> <span data-ttu-id="965da-106">Используйте [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="965da-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="965da-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="965da-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="965da-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="965da-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="965da-109">[in] Структура типа [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , содержащий открытую часть пары ключей, использованного для создания подписи строгого имени.</span><span class="sxs-lookup"><span data-stu-id="965da-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="965da-110">[in] Размер в байтах из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="965da-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="965da-111">[out] Токен строгое имя, соответствующее ключу, переданный в `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="965da-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="965da-112">Среда CLR выделяет память, в котором для возврата токена.</span><span class="sxs-lookup"><span data-stu-id="965da-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="965da-113">Вызывающий объект должен освободить эту память с помощью [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="965da-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="965da-114">[out] Размер в байтах, возвращенный строгое имя маркера.</span><span class="sxs-lookup"><span data-stu-id="965da-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="965da-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="965da-115">Return Value</span></span>  
 `true` <span data-ttu-id="965da-116">После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="965da-116">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="965da-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="965da-117">Remarks</span></span>  
 <span data-ttu-id="965da-118">Маркер строгого имени — это сокращенная форма открытого ключа, используемого для экономии места, при сохранении информации ключа в метаданных.</span><span class="sxs-lookup"><span data-stu-id="965da-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="965da-119">В частности маркеры строгого имени используются в ссылках сборок для ссылки на зависимые сборки.</span><span class="sxs-lookup"><span data-stu-id="965da-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="965da-120">Если `StrongNameTokenFromPublicKey` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="965da-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="965da-121">Требования</span><span class="sxs-lookup"><span data-stu-id="965da-121">Requirements</span></span>  
 <span data-ttu-id="965da-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="965da-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="965da-123">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="965da-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="965da-124">**Библиотека:** Включена как ресурс в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="965da-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 **<span data-ttu-id="965da-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="965da-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="965da-126">См. также</span><span class="sxs-lookup"><span data-stu-id="965da-126">See also</span></span>

- [<span data-ttu-id="965da-127">Метод StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="965da-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="965da-128">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="965da-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="965da-129">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="965da-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
