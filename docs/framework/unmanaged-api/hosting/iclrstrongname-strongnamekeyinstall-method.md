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
ms.openlocfilehash: 693a5831934647256ac48c8f3a2d30325dee4349
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135038"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="5fb18-102">Метод ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="5fb18-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="5fb18-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="5fb18-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fb18-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fb18-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fb18-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="5fb18-106">окне Имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="5fb18-106">[in] The name of the key container.</span></span> <span data-ttu-id="5fb18-107">`wszKeyContainer` должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="5fb18-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5fb18-108">окне Пара двоичных ключей.</span><span class="sxs-lookup"><span data-stu-id="5fb18-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5fb18-109">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="5fb18-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fb18-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5fb18-110">Return Value</span></span>  
 <span data-ttu-id="5fb18-111">`S_OK`, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](https://go.microsoft.com/fwlink/?LinkId=213878) для списка).</span><span class="sxs-lookup"><span data-stu-id="5fb18-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fb18-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="5fb18-112">Remarks</span></span>  
 <span data-ttu-id="5fb18-113">Чтобы удалить контейнер ключей, используйте метод [метод iclrstrongname:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5fb18-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fb18-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5fb18-114">Requirements</span></span>  
 <span data-ttu-id="5fb18-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fb18-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fb18-116">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="5fb18-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5fb18-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5fb18-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5fb18-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fb18-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fb18-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5fb18-119">See also</span></span>

- [<span data-ttu-id="5fb18-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="5fb18-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="5fb18-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5fb18-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
