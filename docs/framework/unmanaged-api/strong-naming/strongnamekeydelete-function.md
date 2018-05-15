---
title: Функция StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a35ec4e3c3110616ac20cd31db134371838deda0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="591ac-102">Функция StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="591ac-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="591ac-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="591ac-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="591ac-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="591ac-104">This function has been deprecated.</span></span> <span data-ttu-id="591ac-105">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="591ac-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="591ac-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="591ac-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="591ac-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="591ac-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="591ac-108">[in] Имя контейнера ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="591ac-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="591ac-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="591ac-109">Return Value</span></span>  
 <span data-ttu-id="591ac-110">`true` При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="591ac-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="591ac-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="591ac-111">Remarks</span></span>  
 <span data-ttu-id="591ac-112">Используйте [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) функции importa пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="591ac-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="591ac-113">Если `StrongNameKeyDelete` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="591ac-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="591ac-114">Требования</span><span class="sxs-lookup"><span data-stu-id="591ac-114">Requirements</span></span>  
 <span data-ttu-id="591ac-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="591ac-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="591ac-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="591ac-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="591ac-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="591ac-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="591ac-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="591ac-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="591ac-119">См. также</span><span class="sxs-lookup"><span data-stu-id="591ac-119">See Also</span></span>  
 [<span data-ttu-id="591ac-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="591ac-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="591ac-121">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="591ac-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="591ac-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="591ac-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
