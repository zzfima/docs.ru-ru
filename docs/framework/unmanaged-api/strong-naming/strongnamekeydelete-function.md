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
ms.openlocfilehash: 3eace88e5034c61b7608a6d777608cc2544b8564
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688484"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="97cbb-102">Функция StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="97cbb-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="97cbb-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="97cbb-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="97cbb-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="97cbb-104">This function has been deprecated.</span></span> <span data-ttu-id="97cbb-105">Используйте [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="97cbb-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97cbb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97cbb-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97cbb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="97cbb-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="97cbb-108">[in] Имя контейнера ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="97cbb-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97cbb-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="97cbb-109">Return Value</span></span>  
 <span data-ttu-id="97cbb-110">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="97cbb-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97cbb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="97cbb-111">Remarks</span></span>  
 <span data-ttu-id="97cbb-112">Используйте [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) функции importa пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="97cbb-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="97cbb-113">Если `StrongNameKeyDelete` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="97cbb-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97cbb-114">Требования</span><span class="sxs-lookup"><span data-stu-id="97cbb-114">Requirements</span></span>  
 <span data-ttu-id="97cbb-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97cbb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97cbb-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="97cbb-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="97cbb-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="97cbb-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97cbb-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97cbb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97cbb-119">См. также</span><span class="sxs-lookup"><span data-stu-id="97cbb-119">See also</span></span>
- [<span data-ttu-id="97cbb-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="97cbb-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="97cbb-121">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="97cbb-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="97cbb-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="97cbb-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
