---
title: Метод ICLRStrongName::StrongNameGetBlobFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd6cb0116e1080a68c91df365cc7dd1485b21791
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421545"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="90259-102">Метод ICLRStrongName::StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="90259-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="90259-103">Возвращает двоичное представление образа сборки по указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="90259-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90259-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90259-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90259-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="90259-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="90259-106">[in] Адрес памяти, сопоставленной сборки манифеста.</span><span class="sxs-lookup"><span data-stu-id="90259-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="90259-107">[in] Размер в байтах, изображения в `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="90259-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="90259-108">[in] Буфер, содержащий двоичное представление изображения.</span><span class="sxs-lookup"><span data-stu-id="90259-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="90259-109">[in, out] Максимальный размер в байтах, запрошенную `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="90259-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="90259-110">По возвращении фактический размер в байтах из `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="90259-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90259-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="90259-111">Return Value</span></span>  
 <span data-ttu-id="90259-112">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="90259-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90259-113">Требования</span><span class="sxs-lookup"><span data-stu-id="90259-113">Requirements</span></span>  
 <span data-ttu-id="90259-114">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90259-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90259-115">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="90259-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="90259-116">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="90259-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="90259-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90259-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90259-118">См. также</span><span class="sxs-lookup"><span data-stu-id="90259-118">See Also</span></span>  
 [<span data-ttu-id="90259-119">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="90259-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="90259-120">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="90259-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
