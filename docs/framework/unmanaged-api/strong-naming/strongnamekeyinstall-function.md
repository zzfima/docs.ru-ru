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
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636707"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="9449a-102">Функция StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="9449a-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="9449a-103">Импортирует пару открытого и закрытого ключей в контейнер.</span><span class="sxs-lookup"><span data-stu-id="9449a-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="9449a-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="9449a-104">This function has been deprecated.</span></span> <span data-ttu-id="9449a-105">Используйте [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9449a-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="9449a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9449a-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="9449a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="9449a-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="9449a-108">[in] Имя контейнера ключа.</span><span class="sxs-lookup"><span data-stu-id="9449a-108">[in] The name of the key container.</span></span> <span data-ttu-id="9449a-109">`wszKeyContainer` должен быть непустой строкой.</span><span class="sxs-lookup"><span data-stu-id="9449a-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="9449a-110">[in] Двоичный пару ключей.</span><span class="sxs-lookup"><span data-stu-id="9449a-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="9449a-111">[in] Размер в байтах из `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="9449a-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9449a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9449a-112">Return Value</span></span>

<span data-ttu-id="9449a-113">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="9449a-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9449a-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="9449a-114">Remarks</span></span>

<span data-ttu-id="9449a-115">Используйте [StrongNameKeyDelete](strongnamekeydelete-function.md) функции, чтобы удалить контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="9449a-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="9449a-116">Если `StrongNameKeyInstall` функция не завершена, вызвать [StrongNameErrorInfo](strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="9449a-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="9449a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="9449a-117">Requirements</span></span>

<span data-ttu-id="9449a-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9449a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9449a-119">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9449a-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="9449a-120">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9449a-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="9449a-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9449a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9449a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9449a-122">See also</span></span>

- [<span data-ttu-id="9449a-123">Метод StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="9449a-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="9449a-124">Метод StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="9449a-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="9449a-125">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="9449a-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
