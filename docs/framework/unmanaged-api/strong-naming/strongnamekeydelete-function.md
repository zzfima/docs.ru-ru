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
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040772"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="fb7c2-102">Функция StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="fb7c2-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="fb7c2-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-103">Deletes the specified key container.</span></span>

<span data-ttu-id="fb7c2-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-104">This function has been deprecated.</span></span> <span data-ttu-id="fb7c2-105">Используйте [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb7c2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb7c2-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="fb7c2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb7c2-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="fb7c2-108">[in] Имя контейнера ключа для удаления.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="fb7c2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fb7c2-109">Return Value</span></span>

<span data-ttu-id="fb7c2-110">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb7c2-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb7c2-111">Remarks</span></span>

<span data-ttu-id="fb7c2-112">Используйте [StrongNameKeyInstall](strongnamekeyinstall-function.md) для импорта пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="fb7c2-113">Если `StrongNameKeyDelete` функция не завершена, вызвать [StrongNameErrorInfo](strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="fb7c2-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb7c2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fb7c2-114">Requirements</span></span>

<span data-ttu-id="fb7c2-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb7c2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="fb7c2-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="fb7c2-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="fb7c2-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fb7c2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="fb7c2-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb7c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fb7c2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="fb7c2-119">See also</span></span>

- [<span data-ttu-id="fb7c2-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="fb7c2-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="fb7c2-121">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="fb7c2-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="fb7c2-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="fb7c2-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)