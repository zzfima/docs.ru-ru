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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140712"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="cbf64-102">Функция GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="cbf64-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="cbf64-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="cbf64-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="cbf64-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="cbf64-104">This function has been deprecated.</span></span> <span data-ttu-id="cbf64-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cbf64-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbf64-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbf64-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="cbf64-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbf64-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="cbf64-108">окне Указатель на адрес блока памяти, который необходимо хэшировать.</span><span class="sxs-lookup"><span data-stu-id="cbf64-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="cbf64-109">окне Длина блока памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="cbf64-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="cbf64-110">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="cbf64-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cbf64-111">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cbf64-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="cbf64-112">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="cbf64-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="cbf64-113">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cbf64-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="cbf64-114">заполняет Размер возвращаемого `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="cbf64-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="cbf64-115">Требования</span><span class="sxs-lookup"><span data-stu-id="cbf64-115">Requirements</span></span>

<span data-ttu-id="cbf64-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbf64-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="cbf64-117">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="cbf64-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="cbf64-118">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cbf64-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="cbf64-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbf64-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cbf64-120">См. также</span><span class="sxs-lookup"><span data-stu-id="cbf64-120">See also</span></span>

- [<span data-ttu-id="cbf64-121">Метод GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="cbf64-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="cbf64-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cbf64-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
