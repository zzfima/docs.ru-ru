---
title: Функция CompareAssemblyIdentity
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: f6711902fb9d5c5c16084057b731746843cf0230
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108919"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="a195b-102">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="a195b-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="a195b-103">Сравнивает два идентификатора сборки, чтобы определить, являются ли они эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="a195b-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a195b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a195b-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="a195b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a195b-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="a195b-106">окне Текстовое удостоверение первой сборки в сравнении.</span><span class="sxs-lookup"><span data-stu-id="a195b-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="a195b-107">окне Логический флаг, указывающий, что для `pwzAssemblyIdentity1`указана пользовательская унификация.</span><span class="sxs-lookup"><span data-stu-id="a195b-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="a195b-108">окне Текстовое удостоверение второй сборки в сравнении.</span><span class="sxs-lookup"><span data-stu-id="a195b-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="a195b-109">окне Логический флаг, указывающий, что для `pwzAssemblyIdentity2`указана пользовательская унификация.</span><span class="sxs-lookup"><span data-stu-id="a195b-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="a195b-110">заполняет Логический флаг, указывающий, эквивалентны ли две сборки.</span><span class="sxs-lookup"><span data-stu-id="a195b-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="a195b-111">заполняет Перечисление [ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md) , содержащее подробные сведения о сравнении.</span><span class="sxs-lookup"><span data-stu-id="a195b-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a195b-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a195b-112">Return Value</span></span>  
 <span data-ttu-id="a195b-113">`pfEquivalent` возвращает логическое значение, указывающее, эквивалентны ли две сборки.</span><span class="sxs-lookup"><span data-stu-id="a195b-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="a195b-114">`pResult` возвращает одно из значений `AssemblyComparisonResult`, чтобы получить более подробную причину для значения `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="a195b-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a195b-115">Заметки</span><span class="sxs-lookup"><span data-stu-id="a195b-115">Remarks</span></span>  
 <span data-ttu-id="a195b-116">`CompareAssemblyIdentity` проверяет, эквивалентны ли `pwzAssemblyIdentity1` и `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="a195b-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="a195b-117">`pfEquivalent` имеет значение `true` в одном или нескольких из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="a195b-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="a195b-118">Два удостоверения сборки эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="a195b-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="a195b-119">Для строго именованных сборок эквивалентность требует идентичности имени сборки, версии, токена открытого ключа и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a195b-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="a195b-120">Для просто именованных сборок эквивалентность требует соответствия имени сборки и языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="a195b-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="a195b-121">Оба удостоверения сборки ссылаются на сборки, которые выполняются в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a195b-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="a195b-122">Это условие возвращает `true` даже в том случае, если номера версий сборки не совпадают.</span><span class="sxs-lookup"><span data-stu-id="a195b-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="a195b-123">Эти две сборки не являются управляемыми сборками, но для `fUnified1` или `fUnified2` задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a195b-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="a195b-124">Флаг `fUnified` указывает, что все номера версий, вплоть до номера версии строго именованной сборки, считаются эквивалентными строго именованной сборке.</span><span class="sxs-lookup"><span data-stu-id="a195b-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="a195b-125">Например, если значение `pwzAssemblyIndentity1` равно "MyAssembly, Version = 3.0.0.0, культура = Neutral, publicKeyToken =....", а значение `fUnified1` — `true`, это означает, что все версии MyAssembly из версии 0.0.0.0 в 3.0.0.0 должны рассматриваться как друг.</span><span class="sxs-lookup"><span data-stu-id="a195b-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="a195b-126">В этом случае, если `pwzAssemblyIndentity2` ссылается на ту же сборку, что и `pwzAssemblyIndentity1`, за исключением того, что имеет меньший номер версии, `pfEquivalent` устанавливается в `true`.</span><span class="sxs-lookup"><span data-stu-id="a195b-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="a195b-127">Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии, `pfEquivalent` устанавливается в `true` только в том случае, если `fUnified2` имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a195b-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="a195b-128">Параметр `pResult` содержит конкретные сведения о том, почему две сборки считаются эквивалентными или не эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="a195b-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="a195b-129">Дополнительные сведения см. в разделе [перечисление ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="a195b-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a195b-130">Требования</span><span class="sxs-lookup"><span data-stu-id="a195b-130">Requirements</span></span>  
 <span data-ttu-id="a195b-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a195b-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a195b-132">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a195b-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a195b-133">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a195b-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a195b-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a195b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a195b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a195b-135">See also</span></span>

- [<span data-ttu-id="a195b-136">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="a195b-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="a195b-137">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="a195b-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
