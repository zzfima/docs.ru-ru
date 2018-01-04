---
title: "Функция StrongNameKeyGenEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyGenEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyGenEx
helpviewer_keywords: StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae564f7c4e8333e33b2f2f6229034c3a1396a687
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeygenex-function"></a><span data-ttu-id="91439-102">Функция StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="91439-102">StrongNameKeyGenEx Function</span></span>
<span data-ttu-id="91439-103">Создает новую пару открытого и закрытого ключей с указанным размером ключа, для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="91439-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
 <span data-ttu-id="91439-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="91439-104">This function has been deprecated.</span></span> <span data-ttu-id="91439-105">Используйте [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="91439-105">Use the [ICLRStrongName::StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91439-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91439-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91439-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="91439-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="91439-108">[in] Имя запрашиваемый контейнер ключа.</span><span class="sxs-lookup"><span data-stu-id="91439-108">[in] The requested key container name.</span></span> <span data-ttu-id="91439-109">`wszKeyContainer`должен быть непустой строкой, или значение null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="91439-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="91439-110">[in] Указывает, следует ли оставлять ключ зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="91439-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="91439-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="91439-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="91439-112">0x00000000 — используется, когда `wszKeyContainer` имеет значение null для создания временного имени контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="91439-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="91439-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="91439-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="91439-114">[in] Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="91439-114">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="91439-115">[out] Возвращаемый открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="91439-115">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="91439-116">[out] Размер в байтах для `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="91439-116">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91439-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="91439-117">Return Value</span></span>  
 <span data-ttu-id="91439-118">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="91439-118">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91439-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="91439-119">Remarks</span></span>  
 <span data-ttu-id="91439-120">Требуется платформа .NET Framework версии 1.0 и 1.1 `dwKeySize` 1024 бит для подписи сборки строгим именем; версии 2.0 добавлена поддержка 2048-разрядные ключи.</span><span class="sxs-lookup"><span data-stu-id="91439-120">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="91439-121">После извлечения ключа необходимо вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="91439-121">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="91439-122">Если `StrongNameKeyGenEx` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="91439-122">If the `StrongNameKeyGenEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91439-123">Требования</span><span class="sxs-lookup"><span data-stu-id="91439-123">Requirements</span></span>  
 <span data-ttu-id="91439-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91439-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91439-125">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="91439-125">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="91439-126">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91439-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91439-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91439-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91439-128">См. также</span><span class="sxs-lookup"><span data-stu-id="91439-128">See Also</span></span>  
 [<span data-ttu-id="91439-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="91439-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="91439-130">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="91439-130">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="91439-131">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="91439-131">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
