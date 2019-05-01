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
ms.openlocfilehash: af75a645b11325b96740807f9a3df65f5a676026
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000250"
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="9355b-102">Функция StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="9355b-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="9355b-103">Создает новую пару открытого и закрытого ключа с заданным размером ключа, для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="9355b-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="9355b-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9355b-104">This function has been deprecated.</span></span> <span data-ttu-id="9355b-105">Используйте [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9355b-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9355b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9355b-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9355b-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9355b-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9355b-108">[in] Имя запрошенного контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="9355b-108">[in] The requested key container name.</span></span> <span data-ttu-id="9355b-109">`wszKeyContainer` должен быть непустой строкой, или значение null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="9355b-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9355b-110">[in] Указывает, следует ли оставить ключ зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="9355b-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="9355b-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="9355b-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="9355b-112">0x00000000 — используется, когда `wszKeyContainer` имеет значение null, если для создания временного имени контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="9355b-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="9355b-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="9355b-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="9355b-114">[in] Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="9355b-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="9355b-115">[out] Возвращаемый ключа пары открытого и закрытого.</span><span class="sxs-lookup"><span data-stu-id="9355b-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="9355b-116">[out] Размер в байтах из `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9355b-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9355b-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9355b-117">Return Value</span></span>  
 <span data-ttu-id="9355b-118">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9355b-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9355b-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="9355b-119">Remarks</span></span>  
 <span data-ttu-id="9355b-120">Требуется .NET Framework версий 1.0 и 1.1 `dwKeySize` 1024 бит для подписи сборки строгим именем; версии 2.0 добавлена поддержка 2048-разрядные ключи.</span><span class="sxs-lookup"><span data-stu-id="9355b-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="9355b-121">После извлечения ключа должно вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="9355b-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="9355b-122">Если `StrongNameKeyGenEx` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="9355b-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9355b-123">Требования</span><span class="sxs-lookup"><span data-stu-id="9355b-123">Requirements</span></span>  
 <span data-ttu-id="9355b-124">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9355b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9355b-125">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9355b-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9355b-126">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9355b-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9355b-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9355b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9355b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9355b-128">See also</span></span>

- [<span data-ttu-id="9355b-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="9355b-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="9355b-130">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="9355b-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="9355b-131">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9355b-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
