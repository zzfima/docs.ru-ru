---
title: Метод ICLRStrongName::StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 540fda24a8085a3066dc0485228d3ea3bc56fb98
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747788"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="c902a-102">Метод ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="c902a-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="c902a-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="c902a-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c902a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c902a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c902a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c902a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c902a-106">[in] Имя контейнера ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="c902a-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c902a-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c902a-107">Return Value</span></span>  
 <span data-ttu-id="c902a-108">`S_OK` Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (см. в разделе [часто встречающихся значений HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="c902a-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c902a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c902a-109">Remarks</span></span>  
 <span data-ttu-id="c902a-110">Используйте [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) метод, чтобы импортировать пару открытого и закрытого ключей в контейнере.</span><span class="sxs-lookup"><span data-stu-id="c902a-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c902a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c902a-111">Requirements</span></span>  
 <span data-ttu-id="c902a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c902a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c902a-113">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c902a-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c902a-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c902a-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c902a-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c902a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c902a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c902a-116">See also</span></span>

- [<span data-ttu-id="c902a-117">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="c902a-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="c902a-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c902a-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
