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
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899557"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="c279c-102">Метод ICLRStrongName::StrongNameKeyGenEx</span><span class="sxs-lookup"><span data-stu-id="c279c-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="c279c-103">Создает новую пару открытого и закрытого ключей с указанным размером ключа для использования строгого имени.</span><span class="sxs-lookup"><span data-stu-id="c279c-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c279c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c279c-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c279c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c279c-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c279c-106">окне Запрошенное имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="c279c-106">[in] The requested key container name.</span></span> <span data-ttu-id="c279c-107">`wszKeyContainer` должен быть непустой строкой или иметь значение NULL для создания временного имени.</span><span class="sxs-lookup"><span data-stu-id="c279c-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c279c-108">окне Значение типа, указывающее, следует ли оставлять зарегистрированный ключ.</span><span class="sxs-lookup"><span data-stu-id="c279c-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="c279c-109">Поддерживаются следующие значения.</span><span class="sxs-lookup"><span data-stu-id="c279c-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="c279c-110">0x00000000 — используется, если `wszKeyContainer` имеет значение NULL для создания временного имени контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="c279c-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="c279c-111">0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.</span><span class="sxs-lookup"><span data-stu-id="c279c-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="c279c-112">окне Запрошенный размер ключа в битах.</span><span class="sxs-lookup"><span data-stu-id="c279c-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="c279c-113">заполняет Возвращаемая пара открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="c279c-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="c279c-114">заполняет Размер `ppbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="c279c-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c279c-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c279c-115">Return Value</span></span>  
 <span data-ttu-id="c279c-116">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="c279c-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c279c-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="c279c-117">Remarks</span></span>  
 <span data-ttu-id="c279c-118">Для подписи сборки строгим именем в .NET Framework версиях 1,0 и 1,1 требуется `dwKeySize` 1024 бит. в версии 2,0 добавлена поддержка для 2048-разрядных ключей.</span><span class="sxs-lookup"><span data-stu-id="c279c-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="c279c-119">После извлечения ключа необходимо вызвать метод [метод iclrstrongname:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) , чтобы освободить выделенную память.</span><span class="sxs-lookup"><span data-stu-id="c279c-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c279c-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c279c-120">Requirements</span></span>  
 <span data-ttu-id="c279c-121">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c279c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c279c-122">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="c279c-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c279c-123">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c279c-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c279c-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c279c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c279c-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="c279c-125">See also</span></span>

- [<span data-ttu-id="c279c-126">Метод StrongNameKeyGen</span><span class="sxs-lookup"><span data-stu-id="c279c-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="c279c-127">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c279c-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
