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
ms.openlocfilehash: a8ebecce4078ba6c2b59e6bfba2d54300ba0c4ee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107384"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="0137e-102">Функция StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="0137e-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="0137e-103">Создает пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="0137e-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="0137e-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="0137e-104">This function has been deprecated.</span></span> <span data-ttu-id="0137e-105">Используйте [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="0137e-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0137e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0137e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0137e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0137e-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="0137e-108">[in] Имя запрошенного контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="0137e-108">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="0137e-109">должен быть непустой строкой, или значение null для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="0137e-109">must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0137e-110">[in] Указывает, следует ли оставить ключ зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="0137e-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="0137e-111">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0137e-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="0137e-112">0x00000000 — используется, когда `wszKeyContainer` имеет значение null, если для создания временного имени контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="0137e-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="0137e-113">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="0137e-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="0137e-114">[out] Возвращаемый ключа пары открытого и закрытого.</span><span class="sxs-lookup"><span data-stu-id="0137e-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="0137e-115">[out] Размер в байтах из `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="0137e-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0137e-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0137e-116">Return Value</span></span>  
 `true` <span data-ttu-id="0137e-117">После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="0137e-117">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0137e-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="0137e-118">Remarks</span></span>  
 <span data-ttu-id="0137e-119">`StrongNameKeyGen` Функция создает 1024-разрядный ключ.</span><span class="sxs-lookup"><span data-stu-id="0137e-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="0137e-120">После извлечения ключа должно вызвать [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) функции, чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="0137e-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="0137e-121">Если `StrongNameKeyGen` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="0137e-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0137e-122">Требования</span><span class="sxs-lookup"><span data-stu-id="0137e-122">Requirements</span></span>  
 <span data-ttu-id="0137e-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0137e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0137e-124">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="0137e-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0137e-125">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0137e-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0137e-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0137e-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0137e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="0137e-127">See also</span></span>

- [<span data-ttu-id="0137e-128">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="0137e-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="0137e-129">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="0137e-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="0137e-130">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="0137e-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
