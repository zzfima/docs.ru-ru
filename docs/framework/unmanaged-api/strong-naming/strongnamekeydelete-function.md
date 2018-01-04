---
title: "Функция StrongNameKeyDelete"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyDelete
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyDelete
helpviewer_keywords: StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3acd8ae5f330e23642a679962a04ccb4f7e8ec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="460b6-102">Функция StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="460b6-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="460b6-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="460b6-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="460b6-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="460b6-104">This function has been deprecated.</span></span> <span data-ttu-id="460b6-105">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="460b6-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="460b6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="460b6-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="460b6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="460b6-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="460b6-108">[in] Имя контейнера ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="460b6-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="460b6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="460b6-109">Return Value</span></span>  
 <span data-ttu-id="460b6-110">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="460b6-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="460b6-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="460b6-111">Remarks</span></span>  
 <span data-ttu-id="460b6-112">Используйте [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) функции importa пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="460b6-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="460b6-113">Если `StrongNameKeyDelete` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="460b6-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="460b6-114">Требования</span><span class="sxs-lookup"><span data-stu-id="460b6-114">Requirements</span></span>  
 <span data-ttu-id="460b6-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="460b6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="460b6-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="460b6-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="460b6-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="460b6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="460b6-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="460b6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="460b6-119">См. также</span><span class="sxs-lookup"><span data-stu-id="460b6-119">See Also</span></span>  
 [<span data-ttu-id="460b6-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="460b6-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="460b6-121">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="460b6-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="460b6-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="460b6-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
