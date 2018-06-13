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
ms.openlocfilehash: 5fce08434cb8864350fd333dcfcaa388a8031c09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459170"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="fd4f2-102">Функция StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="fd4f2-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="fd4f2-103">Создает новую пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="fd4f2-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-104">This function has been deprecated.</span></span> <span data-ttu-id="fd4f2-105">Используйте [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd4f2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd4f2-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd4f2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd4f2-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="fd4f2-108">[in] Имя запрашиваемый контейнер ключа.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-108">[in] The requested key container name.</span></span> <span data-ttu-id="fd4f2-109">`wszKeyContainer` должен быть непустой строкой, или значение null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fd4f2-110">[in] Указывает, следует ли оставлять ключ зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="fd4f2-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="fd4f2-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="fd4f2-112">0x00000000 — используется, когда `wszKeyContainer` имеет значение null для создания временного имени контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="fd4f2-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="fd4f2-114">[out] Возвращаемый открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="fd4f2-115">[out] Размер в байтах для `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd4f2-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fd4f2-116">Return Value</span></span>  
 <span data-ttu-id="fd4f2-117">`true` При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd4f2-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd4f2-118">Remarks</span></span>  
 <span data-ttu-id="fd4f2-119">`StrongNameKeyGen` Функция создается 1024-разрядный ключ.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="fd4f2-120">После извлечения ключа необходимо вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="fd4f2-121">Если `StrongNameKeyGen` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="fd4f2-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd4f2-122">Требования</span><span class="sxs-lookup"><span data-stu-id="fd4f2-122">Requirements</span></span>  
 <span data-ttu-id="fd4f2-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd4f2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd4f2-124">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="fd4f2-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fd4f2-125">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd4f2-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd4f2-126">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd4f2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4f2-127">См. также</span><span class="sxs-lookup"><span data-stu-id="fd4f2-127">See Also</span></span>  
 [<span data-ttu-id="fd4f2-128">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="fd4f2-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="fd4f2-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="fd4f2-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="fd4f2-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="fd4f2-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
