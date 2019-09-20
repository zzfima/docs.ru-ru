---
title: Функция StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0c2e8e46c7bb3a5e693c9ea16e6c5a0722b1898
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799148"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="ecb8e-102">Функция StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="ecb8e-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="ecb8e-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="ecb8e-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-104">This function has been deprecated.</span></span> <span data-ttu-id="ecb8e-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ecb8e-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb8e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecb8e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecb8e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ecb8e-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="ecb8e-108">окне Путь к первой сборке.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="ecb8e-109">окне Путь к второй сборке.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="ecb8e-110">заполняет Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ecb8e-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="ecb8e-111">`SN_CMP_DIFFERENT`(0) — указывает, что сборки содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="ecb8e-112">`SN_CMP_IDENTICAL`(1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="ecb8e-113">`SN_CMP_SIGONLY`(2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecb8e-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ecb8e-114">Return Value</span></span>  
 <span data-ttu-id="ecb8e-115">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="ecb8e-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecb8e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ecb8e-116">Requirements</span></span>  
 <span data-ttu-id="ecb8e-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecb8e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecb8e-118">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="ecb8e-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ecb8e-119">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ecb8e-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ecb8e-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecb8e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecb8e-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="ecb8e-121">Remarks</span></span>  
 <span data-ttu-id="ecb8e-122">Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="ecb8e-123">Если функция `StrongNameCompareAssemblies` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="ecb8e-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb8e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ecb8e-124">See also</span></span>

- [<span data-ttu-id="ecb8e-125">Метод StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="ecb8e-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="ecb8e-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ecb8e-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
