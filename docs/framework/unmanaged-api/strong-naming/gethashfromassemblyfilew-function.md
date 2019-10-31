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
ms.openlocfilehash: cf7667f0f2a0f77cd793e00a5de8b030b0c53ec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140695"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="ec5a3-102">Функция GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="ec5a3-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="ec5a3-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="ec5a3-104">Путь к файлу сборки должен быть указан в виде строки в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="ec5a3-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-105">This function has been deprecated.</span></span> <span data-ttu-id="ec5a3-106">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ec5a3-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec5a3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec5a3-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec5a3-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="ec5a3-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="ec5a3-109">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="ec5a3-110">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="ec5a3-111">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ec5a3-112">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="ec5a3-113">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="ec5a3-114">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="ec5a3-115">заполняет Возвращаемый размер `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="ec5a3-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec5a3-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ec5a3-116">Requirements</span></span>  
 <span data-ttu-id="ec5a3-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec5a3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec5a3-118">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="ec5a3-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ec5a3-119">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec5a3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec5a3-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec5a3-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ec5a3-121">See also</span></span>

- [<span data-ttu-id="ec5a3-122">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="ec5a3-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="ec5a3-123">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="ec5a3-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="ec5a3-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ec5a3-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
