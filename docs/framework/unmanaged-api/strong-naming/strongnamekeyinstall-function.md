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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798994"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="c1627-102">Функция StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="c1627-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="c1627-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="c1627-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="c1627-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="c1627-104">This function has been deprecated.</span></span> <span data-ttu-id="c1627-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c1627-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1627-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1627-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="c1627-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c1627-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="c1627-108">окне Имя контейнера ключей.</span><span class="sxs-lookup"><span data-stu-id="c1627-108">[in] The name of the key container.</span></span> <span data-ttu-id="c1627-109">`wszKeyContainer`значение должно быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="c1627-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="c1627-110">окне Пара двоичных ключей.</span><span class="sxs-lookup"><span data-stu-id="c1627-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="c1627-111">окне Размер (в байтах `pbKeyBlob`).</span><span class="sxs-lookup"><span data-stu-id="c1627-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c1627-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c1627-112">Return Value</span></span>

<span data-ttu-id="c1627-113">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="c1627-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1627-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c1627-114">Remarks</span></span>

<span data-ttu-id="c1627-115">Чтобы удалить контейнер ключей, используйте функцию [StrongNameKeyDelete](strongnamekeydelete-function.md) .</span><span class="sxs-lookup"><span data-stu-id="c1627-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="c1627-116">Если функция `StrongNameKeyInstall` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="c1627-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="c1627-117">Требования</span><span class="sxs-lookup"><span data-stu-id="c1627-117">Requirements</span></span>

<span data-ttu-id="c1627-118">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1627-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c1627-119">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c1627-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="c1627-120">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c1627-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="c1627-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1627-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c1627-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c1627-122">See also</span></span>

- [<span data-ttu-id="c1627-123">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="c1627-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="c1627-124">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="c1627-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="c1627-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="c1627-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
