---
title: Функция StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125201"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="b9df8-102">Функция StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="b9df8-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="b9df8-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="b9df8-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="b9df8-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="b9df8-104">This function has been deprecated.</span></span> <span data-ttu-id="b9df8-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b9df8-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="b9df8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9df8-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="b9df8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9df8-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="b9df8-108">окне Имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="b9df8-108">[in] The name of the key container.</span></span> <span data-ttu-id="b9df8-109">`wszKeyContainer` должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="b9df8-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="b9df8-110">окне Пара двоичных ключей.</span><span class="sxs-lookup"><span data-stu-id="b9df8-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="b9df8-111">окне Размер `pbKeyBlob`в байтах.</span><span class="sxs-lookup"><span data-stu-id="b9df8-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b9df8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9df8-112">Return Value</span></span>

<span data-ttu-id="b9df8-113">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="b9df8-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9df8-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="b9df8-114">Remarks</span></span>

<span data-ttu-id="b9df8-115">Чтобы удалить контейнер ключей, используйте функцию [StrongNameKeyDelete](strongnamekeydelete-function.md) .</span><span class="sxs-lookup"><span data-stu-id="b9df8-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="b9df8-116">Если функция `StrongNameKeyInstall` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="b9df8-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9df8-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b9df8-117">Requirements</span></span>

<span data-ttu-id="b9df8-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9df8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b9df8-119">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="b9df8-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="b9df8-120">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b9df8-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="b9df8-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9df8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b9df8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b9df8-122">See also</span></span>

- [<span data-ttu-id="b9df8-123">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="b9df8-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="b9df8-124">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="b9df8-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="b9df8-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="b9df8-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
