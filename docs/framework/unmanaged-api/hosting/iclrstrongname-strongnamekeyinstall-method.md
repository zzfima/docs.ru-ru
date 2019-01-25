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
ms.openlocfilehash: cadf208fc95cb4c90b0903b0e2de9317ae6b6ec0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735666"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="f93bf-102">Метод ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="f93bf-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="f93bf-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="f93bf-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f93bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f93bf-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f93bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f93bf-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="f93bf-106">[in] Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="f93bf-106">[in] The name of the key container.</span></span> <span data-ttu-id="f93bf-107">`wszKeyContainer` должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="f93bf-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="f93bf-108">[in] Двоичный пару ключей.</span><span class="sxs-lookup"><span data-stu-id="f93bf-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="f93bf-109">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="f93bf-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f93bf-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f93bf-110">Return Value</span></span>  
 <span data-ttu-id="f93bf-111">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="f93bf-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f93bf-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="f93bf-112">Remarks</span></span>  
 <span data-ttu-id="f93bf-113">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метод для удаления контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="f93bf-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f93bf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f93bf-114">Requirements</span></span>  
 <span data-ttu-id="f93bf-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f93bf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f93bf-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f93bf-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f93bf-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f93bf-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f93bf-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f93bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f93bf-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f93bf-119">See also</span></span>
- [<span data-ttu-id="f93bf-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="f93bf-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="f93bf-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f93bf-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
