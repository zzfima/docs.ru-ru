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
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141594"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="123b2-102">Функция StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="123b2-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="123b2-103">Удаляет указанный контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="123b2-103">Deletes the specified key container.</span></span>

<span data-ttu-id="123b2-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="123b2-104">This function has been deprecated.</span></span> <span data-ttu-id="123b2-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .</span><span class="sxs-lookup"><span data-stu-id="123b2-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="123b2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="123b2-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="123b2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="123b2-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="123b2-108">окне Имя удаляемого контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="123b2-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="123b2-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="123b2-109">Return Value</span></span>

<span data-ttu-id="123b2-110">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="123b2-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="123b2-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="123b2-111">Remarks</span></span>

<span data-ttu-id="123b2-112">Используйте функцию [StrongNameKeyInstall](strongnamekeyinstall-function.md) для импорта пары открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="123b2-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="123b2-113">Если функция `StrongNameKeyDelete` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="123b2-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="123b2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="123b2-114">Requirements</span></span>

<span data-ttu-id="123b2-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="123b2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="123b2-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="123b2-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="123b2-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="123b2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="123b2-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="123b2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="123b2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="123b2-119">See also</span></span>

- [<span data-ttu-id="123b2-120">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="123b2-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="123b2-121">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="123b2-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="123b2-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="123b2-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
