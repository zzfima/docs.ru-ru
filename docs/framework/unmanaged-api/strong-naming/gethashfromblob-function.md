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
ms.openlocfilehash: 59b4df08157ce14a58393e54b671e8f41b8998ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799227"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="eb552-102">Функция GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="eb552-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="eb552-103">Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="eb552-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="eb552-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="eb552-104">This function has been deprecated.</span></span> <span data-ttu-id="eb552-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .</span><span class="sxs-lookup"><span data-stu-id="eb552-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb552-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb552-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="eb552-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb552-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="eb552-108">окне Указатель на адрес блока памяти, который необходимо хэшировать.</span><span class="sxs-lookup"><span data-stu-id="eb552-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="eb552-109">окне Длина блока памяти в байтах.</span><span class="sxs-lookup"><span data-stu-id="eb552-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="eb552-110">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="eb552-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="eb552-111">Используйте нуль для алгоритма по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb552-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="eb552-112">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="eb552-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="eb552-113">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="eb552-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="eb552-114">заполняет Размер возвращаемого `pbHash`объекта (в байтах).</span><span class="sxs-lookup"><span data-stu-id="eb552-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="eb552-115">Требования</span><span class="sxs-lookup"><span data-stu-id="eb552-115">Requirements</span></span>

<span data-ttu-id="eb552-116">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb552-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="eb552-117">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="eb552-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="eb552-118">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eb552-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="eb552-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb552-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="eb552-120">См. также</span><span class="sxs-lookup"><span data-stu-id="eb552-120">See also</span></span>

- [<span data-ttu-id="eb552-121">Метод GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="eb552-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="eb552-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="eb552-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
