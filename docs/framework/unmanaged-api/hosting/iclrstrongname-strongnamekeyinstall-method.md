---
title: "Метод ICLRStrongName::StrongNameKeyInstall"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyInstall
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 241421761b87bf9f3baf7315c2ac8e9ebd499486
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="6b2de-102">Метод ICLRStrongName::StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="6b2de-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="6b2de-103">Импортирует пару открытого и закрытого ключей в контейнере.</span><span class="sxs-lookup"><span data-stu-id="6b2de-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b2de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b2de-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b2de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b2de-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="6b2de-106">[in] Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="6b2de-106">[in] The name of the key container.</span></span> <span data-ttu-id="6b2de-107">`wszKeyContainer`должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="6b2de-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="6b2de-108">[in] Двоичный пару ключей.</span><span class="sxs-lookup"><span data-stu-id="6b2de-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="6b2de-109">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="6b2de-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b2de-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6b2de-110">Return Value</span></span>  
 <span data-ttu-id="6b2de-111">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="6b2de-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b2de-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b2de-112">Remarks</span></span>  
 <span data-ttu-id="6b2de-113">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метода для удаления контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="6b2de-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b2de-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6b2de-114">Requirements</span></span>  
 <span data-ttu-id="6b2de-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b2de-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b2de-116">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6b2de-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6b2de-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b2de-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b2de-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b2de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b2de-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6b2de-119">See Also</span></span>  
 [<span data-ttu-id="6b2de-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="6b2de-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="6b2de-121">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="6b2de-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
