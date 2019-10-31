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
ms.openlocfilehash: 4e72818be6808c519677192d3744bbc5ec414d0d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135083"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="61080-102">Метод ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="61080-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="61080-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="61080-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61080-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61080-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61080-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="61080-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="61080-106">окне Имя удаляемого контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="61080-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61080-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="61080-107">Return Value</span></span>  
 <span data-ttu-id="61080-108">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="61080-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61080-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="61080-109">Remarks</span></span>  
 <span data-ttu-id="61080-110">Используйте метод [метод iclrstrongname:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) для импорта пары открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="61080-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61080-111">Требования</span><span class="sxs-lookup"><span data-stu-id="61080-111">Requirements</span></span>  
 <span data-ttu-id="61080-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61080-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61080-113">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="61080-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="61080-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="61080-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61080-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61080-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61080-116">См. также</span><span class="sxs-lookup"><span data-stu-id="61080-116">See also</span></span>

- [<span data-ttu-id="61080-117">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="61080-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="61080-118">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="61080-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
