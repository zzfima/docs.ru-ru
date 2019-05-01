---
title: Метод ICLRStrongName::StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 415df9928572e095c529119bf2e726fa383577b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992983"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="15fcd-102">Метод ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="15fcd-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="15fcd-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="15fcd-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15fcd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15fcd-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15fcd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15fcd-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="15fcd-106">[in] Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="15fcd-106">[in] The name of the key container.</span></span> <span data-ttu-id="15fcd-107">`wszKeyContainer` должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="15fcd-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="15fcd-108">[in] Двоичный пару ключей.</span><span class="sxs-lookup"><span data-stu-id="15fcd-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="15fcd-109">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="15fcd-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15fcd-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="15fcd-110">Return Value</span></span>  
 <span data-ttu-id="15fcd-111">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="15fcd-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15fcd-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="15fcd-112">Remarks</span></span>  
 <span data-ttu-id="15fcd-113">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метод для удаления контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="15fcd-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15fcd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="15fcd-114">Requirements</span></span>  
 <span data-ttu-id="15fcd-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15fcd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15fcd-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="15fcd-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="15fcd-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15fcd-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15fcd-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15fcd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15fcd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="15fcd-119">See also</span></span>

- [<span data-ttu-id="15fcd-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="15fcd-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="15fcd-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="15fcd-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
