---
title: Функция GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4b748370ff1aff042923002ad827a0e39d99963
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799265"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="3ad24-102">Функция GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="3ad24-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="3ad24-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="3ad24-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="3ad24-104">Путь к файлу сборки должен быть указан в виде строки в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="3ad24-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="3ad24-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="3ad24-105">This function has been deprecated.</span></span> <span data-ttu-id="3ad24-106">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3ad24-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ad24-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ad24-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ad24-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="3ad24-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="3ad24-109">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="3ad24-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="3ad24-110">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="3ad24-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="3ad24-111">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="3ad24-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="3ad24-112">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="3ad24-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="3ad24-113">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="3ad24-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="3ad24-114">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="3ad24-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="3ad24-115">заполняет Возвращаемый размер (в байтах) `pbHash`для.</span><span class="sxs-lookup"><span data-stu-id="3ad24-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ad24-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3ad24-116">Requirements</span></span>  
 <span data-ttu-id="3ad24-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ad24-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ad24-118">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="3ad24-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="3ad24-119">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3ad24-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ad24-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ad24-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad24-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3ad24-121">See also</span></span>

- [<span data-ttu-id="3ad24-122">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="3ad24-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="3ad24-123">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="3ad24-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="3ad24-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="3ad24-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
