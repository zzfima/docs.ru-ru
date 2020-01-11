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
ms.openlocfilehash: 95098cbb060c06d2d5a5a4c04b6fa9017bca66a1
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899596"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="34493-102">Метод ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="34493-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="34493-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="34493-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34493-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34493-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34493-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34493-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="34493-106">окне Имя удаляемого контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="34493-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="34493-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="34493-107">Return Value</span></span>  
 <span data-ttu-id="34493-108">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).</span><span class="sxs-lookup"><span data-stu-id="34493-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34493-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="34493-109">Remarks</span></span>  
 <span data-ttu-id="34493-110">Используйте метод [метод iclrstrongname:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) для импорта пары открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="34493-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34493-111">Требования</span><span class="sxs-lookup"><span data-stu-id="34493-111">Requirements</span></span>  
 <span data-ttu-id="34493-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34493-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34493-113">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="34493-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="34493-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="34493-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34493-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34493-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34493-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="34493-116">See also</span></span>

- [<span data-ttu-id="34493-117">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="34493-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="34493-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="34493-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
