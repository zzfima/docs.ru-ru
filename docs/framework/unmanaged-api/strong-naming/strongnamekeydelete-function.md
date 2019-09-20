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
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799022"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="18053-102">Функция StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="18053-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="18053-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="18053-103">Deletes the specified key container.</span></span>

<span data-ttu-id="18053-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="18053-104">This function has been deprecated.</span></span> <span data-ttu-id="18053-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="18053-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="18053-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18053-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="18053-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="18053-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="18053-108">окне Имя удаляемого контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="18053-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="18053-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="18053-109">Return Value</span></span>

<span data-ttu-id="18053-110">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="18053-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="18053-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="18053-111">Remarks</span></span>

<span data-ttu-id="18053-112">Используйте функцию [StrongNameKeyInstall](strongnamekeyinstall-function.md) для импорта пары открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="18053-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="18053-113">Если функция `StrongNameKeyDelete` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="18053-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="18053-114">Требования</span><span class="sxs-lookup"><span data-stu-id="18053-114">Requirements</span></span>

<span data-ttu-id="18053-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18053-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="18053-116">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="18053-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="18053-117">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="18053-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="18053-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18053-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18053-119">См. также</span><span class="sxs-lookup"><span data-stu-id="18053-119">See also</span></span>

- [<span data-ttu-id="18053-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="18053-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="18053-121">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="18053-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="18053-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="18053-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
