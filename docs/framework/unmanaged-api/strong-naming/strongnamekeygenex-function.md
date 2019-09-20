---
title: Функция StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9ab908866402bd7a883114466f32921321a5ee6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799015"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="d4f13-102">Функция StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="d4f13-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="d4f13-103">Создает новую пару открытого и закрытого ключей с указанным размером ключа для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="d4f13-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="d4f13-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="d4f13-104">This function has been deprecated.</span></span> <span data-ttu-id="d4f13-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d4f13-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f13-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4f13-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4f13-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d4f13-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="d4f13-108">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="d4f13-108">[in] The requested key container name.</span></span> <span data-ttu-id="d4f13-109">`wszKeyContainer`должен быть непустой строкой или иметь значение NULL для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="d4f13-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d4f13-110">окне Указывает, следует ли оставить зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="d4f13-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="d4f13-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d4f13-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="d4f13-112">0x00000000 — используется, `wszKeyContainer` если параметр имеет значение null, чтобы создать имя контейнера временного ключа.</span><span class="sxs-lookup"><span data-stu-id="d4f13-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="d4f13-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="d4f13-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="d4f13-114">окне Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="d4f13-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="d4f13-115">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="d4f13-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="d4f13-116">заполняет Размер (в байтах `ppbKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="d4f13-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4f13-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d4f13-117">Return Value</span></span>  
 <span data-ttu-id="d4f13-118">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="d4f13-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f13-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="d4f13-119">Remarks</span></span>  
 <span data-ttu-id="d4f13-120">Для подписывания сборки строгим именем в `dwKeySize` .NET Framework версиях 1,0 и 1,1 требуется a из 1024 бит. в версии 2,0 добавлена поддержка для 2048-разрядных ключей.</span><span class="sxs-lookup"><span data-stu-id="d4f13-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="d4f13-121">После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="d4f13-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="d4f13-122">Если функция `StrongNameKeyGenEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="d4f13-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4f13-123">Требования</span><span class="sxs-lookup"><span data-stu-id="d4f13-123">Requirements</span></span>  
 <span data-ttu-id="d4f13-124">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4f13-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4f13-125">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d4f13-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d4f13-126">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d4f13-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4f13-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4f13-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f13-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d4f13-128">See also</span></span>

- [<span data-ttu-id="d4f13-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="d4f13-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="d4f13-130">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="d4f13-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="d4f13-131">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d4f13-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
