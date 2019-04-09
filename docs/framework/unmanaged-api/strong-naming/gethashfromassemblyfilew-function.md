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
ms.openlocfilehash: 9a88adec508d80a40ec044e5011d3115e197e334
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137492"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="da8a9-102">Функция GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="da8a9-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="da8a9-103">Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="da8a9-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="da8a9-104">Путь к файлу сборки должен быть указан как строка Юникода.</span><span class="sxs-lookup"><span data-stu-id="da8a9-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="da8a9-105">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="da8a9-105">This function has been deprecated.</span></span> <span data-ttu-id="da8a9-106">Используйте [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="da8a9-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da8a9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da8a9-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da8a9-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="da8a9-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="da8a9-109">[in] Путь к файлу, хэширование которого требуется выполнить.</span><span class="sxs-lookup"><span data-stu-id="da8a9-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="da8a9-110">Этот параметр должен быть строкой Юникода.</span><span class="sxs-lookup"><span data-stu-id="da8a9-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="da8a9-111">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="da8a9-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="da8a9-112">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="da8a9-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="da8a9-113">[out] Буфер, возвращенный хэша.</span><span class="sxs-lookup"><span data-stu-id="da8a9-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="da8a9-114">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="da8a9-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="da8a9-115">[out] Размер в байтах, возвращенное `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="da8a9-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da8a9-116">Требования</span><span class="sxs-lookup"><span data-stu-id="da8a9-116">Requirements</span></span>  
 <span data-ttu-id="da8a9-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da8a9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da8a9-118">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="da8a9-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="da8a9-119">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da8a9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="da8a9-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da8a9-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da8a9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="da8a9-121">See also</span></span>

- [<span data-ttu-id="da8a9-122">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="da8a9-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="da8a9-123">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="da8a9-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="da8a9-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="da8a9-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
