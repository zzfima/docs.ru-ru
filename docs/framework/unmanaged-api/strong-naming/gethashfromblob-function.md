---
title: Функция GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352078"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="d1a3d-102">Функция GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d1a3d-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="d1a3d-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="d1a3d-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-104">This function has been deprecated.</span></span> <span data-ttu-id="d1a3d-105">Используйте [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-105">Use the [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d1a3d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d1a3d-106">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="d1a3d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="d1a3d-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="d1a3d-108">[in] Указатель на адрес блока памяти, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="d1a3d-109">[in] Длина в байтах блока памяти.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="d1a3d-110">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d1a3d-111">Использовать нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="d1a3d-112">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="d1a3d-113">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="d1a3d-114">[out] Размер в байтах, возвращаемого `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d1a3d-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d1a3d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d1a3d-115">Requirements</span></span>

<span data-ttu-id="d1a3d-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1a3d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d1a3d-117">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d1a3d-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="d1a3d-118">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1a3d-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="d1a3d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a3d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d1a3d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d1a3d-120">See also</span></span>

- [<span data-ttu-id="d1a3d-121">Метод GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="d1a3d-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="d1a3d-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="d1a3d-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)