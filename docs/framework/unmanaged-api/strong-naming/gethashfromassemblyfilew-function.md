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
ms.openlocfilehash: 832d66eee14680870e70f1e0e8d40987eff3257f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457578"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="cdd53-102">Функция GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="cdd53-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="cdd53-103">Возвращает хэш файла указанную сборку, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="cdd53-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="cdd53-104">Путь к файлу сборки необходимо указать как строка Юникода.</span><span class="sxs-lookup"><span data-stu-id="cdd53-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="cdd53-105">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="cdd53-105">This function has been deprecated.</span></span> <span data-ttu-id="cdd53-106">Используйте [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="cdd53-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdd53-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdd53-107">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdd53-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="cdd53-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cdd53-109">[in] Путь к файлу для хэширования.</span><span class="sxs-lookup"><span data-stu-id="cdd53-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="cdd53-110">Этот параметр должен быть строкой в Юникоде.</span><span class="sxs-lookup"><span data-stu-id="cdd53-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cdd53-111">[in, out] Константа, указывающая хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="cdd53-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cdd53-112">Использовать нуль для хэш-алгоритм по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdd53-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cdd53-113">[out] Буфер, возвращенный хэш.</span><span class="sxs-lookup"><span data-stu-id="cdd53-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cdd53-114">[in] Запрошенный максимальный размер `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cdd53-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cdd53-115">[out] Возвращаемый размер в байтах для `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="cdd53-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdd53-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cdd53-116">Requirements</span></span>  
 <span data-ttu-id="cdd53-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdd53-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdd53-118">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="cdd53-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cdd53-119">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cdd53-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cdd53-120">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdd53-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd53-121">См. также</span><span class="sxs-lookup"><span data-stu-id="cdd53-121">See Also</span></span>  
 [<span data-ttu-id="cdd53-122">Метод GetHashFromAssemblyFileW</span><span class="sxs-lookup"><span data-stu-id="cdd53-122">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="cdd53-123">Метод GetHashFromAssemblyFile</span><span class="sxs-lookup"><span data-stu-id="cdd53-123">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="cdd53-124">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="cdd53-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
