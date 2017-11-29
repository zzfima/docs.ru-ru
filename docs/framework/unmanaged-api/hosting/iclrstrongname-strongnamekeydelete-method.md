---
title: "Метод ICLRStrongName::StrongNameKeyDelete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyDelete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8fbb6af492007eb0dc2a9ea83c53e3559225428d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="9a6c8-102">Метод ICLRStrongName::StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="9a6c8-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="9a6c8-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a6c8-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a6c8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a6c8-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="9a6c8-106">[in] Имя контейнера ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a6c8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a6c8-107">Return Value</span></span>  
 <span data-ttu-id="9a6c8-108">`S_OK`Если метод успешно завершена; в противном случае — значение HRESULT, указывающее на сбой (в разделе [часто встречающихся значений HRESULT](http://go.microsoft.com/fwlink/?LinkId=213878) список).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a6c8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a6c8-109">Remarks</span></span>  
 <span data-ttu-id="9a6c8-110">Используйте [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) метод, чтобы импортировать пару открытого и закрытого ключей в контейнере.</span><span class="sxs-lookup"><span data-stu-id="9a6c8-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a6c8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9a6c8-111">Requirements</span></span>  
 <span data-ttu-id="9a6c8-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a6c8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6c8-113">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9a6c8-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9a6c8-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9a6c8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a6c8-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6c8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6c8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9a6c8-116">See Also</span></span>  
 [<span data-ttu-id="9a6c8-117">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="9a6c8-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="9a6c8-118">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9a6c8-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
