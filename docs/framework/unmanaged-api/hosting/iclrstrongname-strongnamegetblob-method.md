---
title: Метод ICLRStrongName::StrongNameGetBlob
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3caa9e6f45368f4d09ed79159c650aac1e5b25e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678542"
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="42e08-102">Метод ICLRStrongName::StrongNameGetBlob</span><span class="sxs-lookup"><span data-stu-id="42e08-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="42e08-103">Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="42e08-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42e08-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42e08-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42e08-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="42e08-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="42e08-106">[in] Допустимый путь к исполняемому файлу для загрузки.</span><span class="sxs-lookup"><span data-stu-id="42e08-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="42e08-107">[in] Буфер, в которой для загрузки исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="42e08-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="42e08-108">[in, out] Максимальный размер в байтах, запрошенную `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="42e08-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="42e08-109">По возвращении фактический размер в байтах из `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="42e08-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42e08-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="42e08-110">Return Value</span></span>  
 <span data-ttu-id="42e08-111">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="42e08-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e08-112">Требования</span><span class="sxs-lookup"><span data-stu-id="42e08-112">Requirements</span></span>  
 <span data-ttu-id="42e08-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e08-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e08-114">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="42e08-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="42e08-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42e08-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42e08-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42e08-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42e08-117">См. также</span><span class="sxs-lookup"><span data-stu-id="42e08-117">See also</span></span>
- [<span data-ttu-id="42e08-118">Метод StrongNameGetBlobFromImage</span><span class="sxs-lookup"><span data-stu-id="42e08-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="42e08-119">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="42e08-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
