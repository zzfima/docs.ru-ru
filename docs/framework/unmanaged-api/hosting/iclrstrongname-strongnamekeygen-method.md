---
title: Метод ICLRStrongName::StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abeb731ecd66e4412f904b085abcfc7b5b3a3c4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665043"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="55e8f-102">Метод ICLRStrongName::StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="55e8f-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="55e8f-103">Создает пару открытого и закрытого ключей для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="55e8f-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55e8f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="55e8f-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55e8f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="55e8f-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="55e8f-106">[in] Имя запрошенного контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="55e8f-106">[in] The requested key container name.</span></span> <span data-ttu-id="55e8f-107">`wszKeyContainer` должен быть непустой строкой или значение null, чтобы создать временное имя.</span><span class="sxs-lookup"><span data-stu-id="55e8f-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="55e8f-108">[in] Значение, указывающее, следует ли оставить ключ зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="55e8f-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="55e8f-109">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="55e8f-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="55e8f-110">0x00000000 — используется, когда `wszKeyContainer` имеет значение null, если для создания временного имени контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="55e8f-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="55e8f-111">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="55e8f-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="55e8f-112">[out] Возвращаемый ключа пары открытого и закрытого.</span><span class="sxs-lookup"><span data-stu-id="55e8f-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="55e8f-113">[out] Размер в байтах из `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="55e8f-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55e8f-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="55e8f-114">Return Value</span></span>  
 <span data-ttu-id="55e8f-115">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="55e8f-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55e8f-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="55e8f-116">Remarks</span></span>  
 <span data-ttu-id="55e8f-117">[ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) метод создает 1024-разрядный ключ.</span><span class="sxs-lookup"><span data-stu-id="55e8f-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="55e8f-118">После извлечения ключа должно вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="55e8f-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55e8f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="55e8f-119">Requirements</span></span>  
 <span data-ttu-id="55e8f-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55e8f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55e8f-121">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="55e8f-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="55e8f-122">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55e8f-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55e8f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55e8f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55e8f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="55e8f-124">See also</span></span>

- [<span data-ttu-id="55e8f-125">Метод StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="55e8f-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="55e8f-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="55e8f-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
