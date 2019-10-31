---
title: Функция GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 866b34acae333f043d8e13f4d0ebd55f32046334
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140728"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="516c5-102">Функция GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="516c5-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="516c5-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="516c5-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="516c5-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="516c5-104">This function has been deprecated.</span></span> <span data-ttu-id="516c5-105">Используйте вместо этого метод [метод iclrstrongname:: GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="516c5-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="516c5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="516c5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="516c5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="516c5-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="516c5-108">окне Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="516c5-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="516c5-109">[вход, выход] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="516c5-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="516c5-110">Для алгоритма хэширования по умолчанию используется нуль.</span><span class="sxs-lookup"><span data-stu-id="516c5-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="516c5-111">заполняет Возвращаемый буфер хэша.</span><span class="sxs-lookup"><span data-stu-id="516c5-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="516c5-112">окне Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="516c5-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="516c5-113">заполняет Возвращаемый размер `pbHash`в байтах.</span><span class="sxs-lookup"><span data-stu-id="516c5-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="516c5-114">Требования</span><span class="sxs-lookup"><span data-stu-id="516c5-114">Requirements</span></span>  
 <span data-ttu-id="516c5-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="516c5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="516c5-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="516c5-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="516c5-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="516c5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="516c5-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="516c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516c5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="516c5-119">See also</span></span>

- [<span data-ttu-id="516c5-120">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="516c5-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="516c5-121">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="516c5-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="516c5-122">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="516c5-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
