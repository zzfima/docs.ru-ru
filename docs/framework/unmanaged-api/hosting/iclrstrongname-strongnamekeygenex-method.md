---
title: Метод ICLRStrongName::StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97e6f16029b9a273a68d52b830939819bfa5380
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083561"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="61cb8-102">Метод ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="61cb8-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="61cb8-103">Создает новую пару открытого и закрытого ключа с заданным размером ключа, для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="61cb8-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61cb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61cb8-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61cb8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61cb8-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="61cb8-106">[in] Имя запрошенного контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="61cb8-106">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="61cb8-107">должен быть непустой строкой или значение null, чтобы создать временное имя.</span><span class="sxs-lookup"><span data-stu-id="61cb8-107">must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="61cb8-108">[in] Значение, указывающее, следует ли оставить ключ зарегистрирован.</span><span class="sxs-lookup"><span data-stu-id="61cb8-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="61cb8-109">Поддерживаются следующие значения:</span><span class="sxs-lookup"><span data-stu-id="61cb8-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="61cb8-110">0x00000000 — используется, когда `wszKeyContainer` имеет значение null, если для создания временного имени контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="61cb8-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="61cb8-111">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="61cb8-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="61cb8-112">[in] Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="61cb8-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="61cb8-113">[out] Возвращаемый ключа пары открытого и закрытого.</span><span class="sxs-lookup"><span data-stu-id="61cb8-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="61cb8-114">[out] Размер в байтах из `ppbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="61cb8-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61cb8-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="61cb8-115">Return Value</span></span>  
 `S_OK` <span data-ttu-id="61cb8-116">Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="61cb8-116">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61cb8-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="61cb8-117">Remarks</span></span>  
 <span data-ttu-id="61cb8-118">Требуется .NET Framework версий 1.0 и 1.1 `dwKeySize` 1024 бит для подписи сборки строгим именем; версии 2.0 добавлена поддержка 2048-разрядные ключи.</span><span class="sxs-lookup"><span data-stu-id="61cb8-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="61cb8-119">После извлечения ключа должно вызвать [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод для освобождения выделенной памяти.</span><span class="sxs-lookup"><span data-stu-id="61cb8-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61cb8-120">Требования</span><span class="sxs-lookup"><span data-stu-id="61cb8-120">Requirements</span></span>  
 <span data-ttu-id="61cb8-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61cb8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61cb8-122">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="61cb8-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="61cb8-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61cb8-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="61cb8-124">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="61cb8-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61cb8-125">См. также</span><span class="sxs-lookup"><span data-stu-id="61cb8-125">See also</span></span>

- [<span data-ttu-id="61cb8-126">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="61cb8-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="61cb8-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="61cb8-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
