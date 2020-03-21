---
title: Метод ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176322"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="9b656-102">Метод ICLRStrongName::StrongNameTokenFromPublicKey</span><span class="sxs-lookup"><span data-stu-id="9b656-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="9b656-103">Получает маркер, представляющий открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="9b656-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="9b656-104">Сильный маркер имени — это укороченная форма клавиши общего пользования.</span><span class="sxs-lookup"><span data-stu-id="9b656-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b656-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b656-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b656-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b656-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="9b656-107">(в) Структура типа [PublicKeyBlob,](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) содержащая публичную часть ключевой пары, используемой для создания сильной подписи имен.</span><span class="sxs-lookup"><span data-stu-id="9b656-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="9b656-108">(в) Размер, в байтах, из `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9b656-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="9b656-109">(ваут) Сильное имя маркер, соответствующий `pbPublicKeyBlob`ключу прошло в .</span><span class="sxs-lookup"><span data-stu-id="9b656-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="9b656-110">Общее время выполнения языка выделяет память, в которой возвращается токен.</span><span class="sxs-lookup"><span data-stu-id="9b656-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="9b656-111">Звонящее должно освободить эту память с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)</span><span class="sxs-lookup"><span data-stu-id="9b656-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="9b656-112">(ваут) Размер, в байтах, возвращенного сильного маркера имени.</span><span class="sxs-lookup"><span data-stu-id="9b656-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b656-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9b656-113">Return Value</span></span>  
 <span data-ttu-id="9b656-114">`S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="9b656-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b656-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b656-115">Remarks</span></span>  
 <span data-ttu-id="9b656-116">Сильный маркер имени — это укороченная форма общедоступного ключа, которая используется для экономии места при хранении ключевой информации в метаданных.</span><span class="sxs-lookup"><span data-stu-id="9b656-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="9b656-117">В частности, сильные маркеры имен используются в ссылках на сборку для обозначения зависимой сборки.</span><span class="sxs-lookup"><span data-stu-id="9b656-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b656-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9b656-118">Requirements</span></span>  
 <span data-ttu-id="9b656-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b656-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b656-120">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9b656-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9b656-121">**Библиотека:** Включено в качестве ресурса в mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9b656-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="9b656-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b656-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b656-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9b656-123">See also</span></span>

- [<span data-ttu-id="9b656-124">Метод StrongNameGetPublicKey</span><span class="sxs-lookup"><span data-stu-id="9b656-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="9b656-125">Структура PublicKeyBlob</span><span class="sxs-lookup"><span data-stu-id="9b656-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="9b656-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9b656-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
