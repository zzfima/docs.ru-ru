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
ms.openlocfilehash: adde52dddb63b83dcd7ff10703a43928d9601c92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140618"
---
# <a name="strongnamecompareassemblies-function"></a><span data-ttu-id="ff31e-102">Функция StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="ff31e-102">StrongNameCompareAssemblies Function</span></span>
<span data-ttu-id="ff31e-103">Определяет, отличаются ли две сборки только подписями строгого имени.</span><span class="sxs-lookup"><span data-stu-id="ff31e-103">Determines whether two assemblies differ only by their strong name signatures.</span></span>  
  
 <span data-ttu-id="ff31e-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="ff31e-104">This function has been deprecated.</span></span> <span data-ttu-id="ff31e-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ff31e-105">Use the [ICLRStrongName::StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff31e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff31e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff31e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff31e-107">Parameters</span></span>  
 `wszAssembly1`  
 <span data-ttu-id="ff31e-108">окне Путь к первой сборке.</span><span class="sxs-lookup"><span data-stu-id="ff31e-108">[in] The path to the first assembly.</span></span>  
  
 `wszAssembly2`  
 <span data-ttu-id="ff31e-109">окне Путь к второй сборке.</span><span class="sxs-lookup"><span data-stu-id="ff31e-109">[in] The path to the second assembly.</span></span>  
  
 `pdwResult`  
 <span data-ttu-id="ff31e-110">заполняет Одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="ff31e-110">[out] One of the following values:</span></span>  
  
- <span data-ttu-id="ff31e-111">`SN_CMP_DIFFERENT` (0) — указывает, что сборки содержат различные данные.</span><span class="sxs-lookup"><span data-stu-id="ff31e-111">`SN_CMP_DIFFERENT` (0) - Specifies that the assemblies contain different data.</span></span>  
  
- <span data-ttu-id="ff31e-112">`SN_CMP_IDENTICAL` (1) — указывает, что сборки точно одинаковы, включая их подписи и контрольные суммы.</span><span class="sxs-lookup"><span data-stu-id="ff31e-112">`SN_CMP_IDENTICAL` (1) - Specifies that the assemblies are exactly the same, including their signatures and checksum.</span></span>  
  
- <span data-ttu-id="ff31e-113">`SN_CMP_SIGONLY` (2) — указывает, что сборки отличаются только сигнатурой и контрольной суммой.</span><span class="sxs-lookup"><span data-stu-id="ff31e-113">`SN_CMP_SIGONLY` (2) - Specifies that the assemblies differ only by signature and checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff31e-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ff31e-114">Return Value</span></span>  
 <span data-ttu-id="ff31e-115">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="ff31e-115">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff31e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ff31e-116">Requirements</span></span>  
 <span data-ttu-id="ff31e-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff31e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff31e-118">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="ff31e-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="ff31e-119">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ff31e-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff31e-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff31e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff31e-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="ff31e-121">Remarks</span></span>  
 <span data-ttu-id="ff31e-122">Подпись строгого имени сборки состоит из текстового имени, версии, языка и региональных параметров сборки, а также токена открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="ff31e-122">The strong name signature of an assembly consists of the assembly's text name, version, culture, and public key token.</span></span>  
  
 <span data-ttu-id="ff31e-123">Если функция `StrongNameCompareAssemblies` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="ff31e-123">If the `StrongNameCompareAssemblies` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff31e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="ff31e-124">See also</span></span>

- [<span data-ttu-id="ff31e-125">Метод StrongNameCompareAssemblies</span><span class="sxs-lookup"><span data-stu-id="ff31e-125">StrongNameCompareAssemblies Method</span></span>](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [<span data-ttu-id="ff31e-126">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="ff31e-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
