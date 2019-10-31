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
ms.openlocfilehash: ad3b151165eb233bd3a4a78d8f4d612a696b7e93
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135100"
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a><span data-ttu-id="35e66-102">Метод ICLRStrongName::StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="35e66-102">ICLRStrongName::StrongNameGetBlobFromImage Method</span></span>
<span data-ttu-id="35e66-103">Получает двоичное представление образа сборки по указанному адресу памяти.</span><span class="sxs-lookup"><span data-stu-id="35e66-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35e66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="35e66-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35e66-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="35e66-105">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="35e66-106">окне Адрес сопоставленного манифеста сборки в памяти.</span><span class="sxs-lookup"><span data-stu-id="35e66-106">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="35e66-107">окне Размер изображения в байтах, в `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="35e66-107">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="35e66-108">окне Буфер для хранения двоичного представления изображения.</span><span class="sxs-lookup"><span data-stu-id="35e66-108">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="35e66-109">[вход, выход] Запрошенный максимальный размер `pbBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="35e66-109">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="35e66-110">При возврате фактический размер (в байтах) `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="35e66-110">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35e66-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="35e66-111">Return Value</span></span>  
 <span data-ttu-id="35e66-112">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="35e66-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35e66-113">Требования</span><span class="sxs-lookup"><span data-stu-id="35e66-113">Requirements</span></span>  
 <span data-ttu-id="35e66-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35e66-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35e66-115">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="35e66-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="35e66-116">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="35e66-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35e66-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35e66-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e66-118">См. также</span><span class="sxs-lookup"><span data-stu-id="35e66-118">See also</span></span>

- [<span data-ttu-id="35e66-119">Метод StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="35e66-119">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="35e66-120">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="35e66-120">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
