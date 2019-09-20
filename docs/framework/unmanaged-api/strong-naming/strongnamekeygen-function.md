---
title: Функция StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f062f47790136e8cd39c6751b7c75eef660c2b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799134"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="d79b6-102">Функция StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="d79b6-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="d79b6-103">Создает пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="d79b6-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="d79b6-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="d79b6-104">This function has been deprecated.</span></span> <span data-ttu-id="d79b6-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d79b6-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79b6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d79b6-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79b6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d79b6-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="d79b6-108">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="d79b6-108">[in] The requested key container name.</span></span> <span data-ttu-id="d79b6-109">`wszKeyContainer`должен быть непустой строкой или иметь значение NULL для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="d79b6-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d79b6-110">окне Указывает, следует ли оставить зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="d79b6-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="d79b6-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d79b6-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="d79b6-112">0x00000000 — используется, `wszKeyContainer` если параметр имеет значение null, чтобы создать имя контейнера временного ключа.</span><span class="sxs-lookup"><span data-stu-id="d79b6-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="d79b6-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="d79b6-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="d79b6-114">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="d79b6-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="d79b6-115">заполняет Размер (в байтах `ppbKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="d79b6-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d79b6-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d79b6-116">Return Value</span></span>  
 <span data-ttu-id="d79b6-117">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="d79b6-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d79b6-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="d79b6-118">Remarks</span></span>  
 <span data-ttu-id="d79b6-119">`StrongNameKeyGen` Функция создает 1024-разрядный ключ.</span><span class="sxs-lookup"><span data-stu-id="d79b6-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="d79b6-120">После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="d79b6-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="d79b6-121">Если функция `StrongNameKeyGen` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="d79b6-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79b6-122">Требования</span><span class="sxs-lookup"><span data-stu-id="d79b6-122">Requirements</span></span>  
 <span data-ttu-id="d79b6-123">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d79b6-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79b6-124">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d79b6-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d79b6-125">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d79b6-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d79b6-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79b6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79b6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d79b6-127">See also</span></span>

- [<span data-ttu-id="d79b6-128">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="d79b6-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="d79b6-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="d79b6-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="d79b6-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d79b6-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
