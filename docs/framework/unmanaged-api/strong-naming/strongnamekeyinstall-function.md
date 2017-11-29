---
title: "Функция StrongNameKeyInstall"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyInstall
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyInstall
helpviewer_keywords: StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60044e12a884a28cb7485118a95d2bf7650723fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="46932-102">Функция StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="46932-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="46932-103">Импортирует пару открытого и закрытого ключей в контейнере.</span><span class="sxs-lookup"><span data-stu-id="46932-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="46932-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="46932-104">This function has been deprecated.</span></span> <span data-ttu-id="46932-105">Используйте [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="46932-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46932-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46932-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46932-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="46932-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="46932-108">[in] Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="46932-108">[in] The name of the key container.</span></span> <span data-ttu-id="46932-109">`wszKeyContainer`должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="46932-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="46932-110">[in] Двоичный пару ключей.</span><span class="sxs-lookup"><span data-stu-id="46932-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="46932-111">[in] Размер в байтах для `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="46932-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46932-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="46932-112">Return Value</span></span>  
 <span data-ttu-id="46932-113">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="46932-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46932-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="46932-114">Remarks</span></span>  
 <span data-ttu-id="46932-115">Используйте [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) функции, чтобы удалить контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="46932-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="46932-116">Если `StrongNameKeyInstall` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="46932-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46932-117">Требования</span><span class="sxs-lookup"><span data-stu-id="46932-117">Requirements</span></span>  
 <span data-ttu-id="46932-118">**Платформы:** WindSee [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46932-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46932-119">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="46932-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="46932-120">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46932-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46932-121">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46932-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46932-122">См. также</span><span class="sxs-lookup"><span data-stu-id="46932-122">See Also</span></span>  
 [<span data-ttu-id="46932-123">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="46932-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="46932-124">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="46932-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="46932-125">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="46932-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
