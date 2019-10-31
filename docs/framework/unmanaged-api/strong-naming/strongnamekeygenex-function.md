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
ms.openlocfilehash: 63ddd90f3a8090853d10f03052915d10e1503ea6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125214"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="31013-102">Функция StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="31013-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="31013-103">Создает новую пару открытого и закрытого ключей с указанным размером ключа для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="31013-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="31013-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="31013-104">This function has been deprecated.</span></span> <span data-ttu-id="31013-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="31013-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31013-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31013-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31013-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="31013-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="31013-108">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="31013-108">[in] The requested key container name.</span></span> <span data-ttu-id="31013-109">`wszKeyContainer` должен быть непустой строкой или иметь значение NULL для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="31013-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="31013-110">окне Указывает, следует ли оставить зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="31013-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="31013-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="31013-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="31013-112">0x00000000 — используется, если `wszKeyContainer` имеет значение NULL для создания временного имени контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="31013-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="31013-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="31013-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="31013-114">окне Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="31013-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="31013-115">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="31013-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="31013-116">заполняет Размер `ppbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="31013-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31013-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="31013-117">Return Value</span></span>  
 <span data-ttu-id="31013-118">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="31013-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31013-119">Заметки</span><span class="sxs-lookup"><span data-stu-id="31013-119">Remarks</span></span>  
 <span data-ttu-id="31013-120">Для подписи сборки строгим именем в .NET Framework версиях 1,0 и 1,1 требуется `dwKeySize` 1024 бит. в версии 2,0 добавлена поддержка для 2048-разрядных ключей.</span><span class="sxs-lookup"><span data-stu-id="31013-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="31013-121">После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="31013-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="31013-122">Если функция `StrongNameKeyGenEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="31013-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31013-123">Требования</span><span class="sxs-lookup"><span data-stu-id="31013-123">Requirements</span></span>  
 <span data-ttu-id="31013-124">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31013-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31013-125">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="31013-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="31013-126">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="31013-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31013-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31013-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31013-128">См. также</span><span class="sxs-lookup"><span data-stu-id="31013-128">See also</span></span>

- [<span data-ttu-id="31013-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="31013-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="31013-130">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="31013-130">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="31013-131">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="31013-131">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
