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
ms.openlocfilehash: 3a2badf8f164abd1bbb8892ec5db28f7cf39f5c5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775664"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="7ea44-102">Метод ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="7ea44-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="7ea44-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="7ea44-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ea44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ea44-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ea44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ea44-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="7ea44-106">[in] Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="7ea44-106">[in] The name of the key container.</span></span> <span data-ttu-id="7ea44-107">`wszKeyContainer` должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="7ea44-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="7ea44-108">[in] Двоичный пару ключей.</span><span class="sxs-lookup"><span data-stu-id="7ea44-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="7ea44-109">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="7ea44-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ea44-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7ea44-110">Return Value</span></span>  
 <span data-ttu-id="7ea44-111">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="7ea44-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ea44-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ea44-112">Remarks</span></span>  
 <span data-ttu-id="7ea44-113">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метод для удаления контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="7ea44-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ea44-114">Требования</span><span class="sxs-lookup"><span data-stu-id="7ea44-114">Requirements</span></span>  
 <span data-ttu-id="7ea44-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ea44-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ea44-116">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7ea44-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7ea44-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7ea44-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ea44-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ea44-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea44-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7ea44-119">See also</span></span>

- [<span data-ttu-id="7ea44-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="7ea44-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="7ea44-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="7ea44-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
