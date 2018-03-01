---
title: "Функция CompareAssemblyIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 266868a65a0db75b57d46d92a469b4b6ceaa88e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="5b368-102">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="5b368-102">CompareAssemblyIdentity Function</span></span>
<span data-ttu-id="5b368-103">Сравнивает два идентификатора сборки, чтобы определить, эквивалентны ли они.</span><span class="sxs-lookup"><span data-stu-id="5b368-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b368-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b368-104">Syntax</span></span>  
  
```  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b368-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b368-105">Parameters</span></span>  
 `pwzAssemblyIdentity1`  
 <span data-ttu-id="5b368-106">[in] Текстовым идентификатором первой сборки в сравнении.</span><span class="sxs-lookup"><span data-stu-id="5b368-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="5b368-107">[in] Логический флаг, который указывает определяемый пользователем унификацию для `pwzAssemblyIdentity1`.</span><span class="sxs-lookup"><span data-stu-id="5b368-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="5b368-108">[in] Текстовым идентификатором вторую сборку для сравнения.</span><span class="sxs-lookup"><span data-stu-id="5b368-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="5b368-109">[in] Логический флаг, который указывает определяемый пользователем унификацию для `pwzAssemblyIdentity2`.</span><span class="sxs-lookup"><span data-stu-id="5b368-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="5b368-110">[out] Логический флаг, указывающее, равны ли две сборки.</span><span class="sxs-lookup"><span data-stu-id="5b368-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="5b368-111">[out] [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) перечисления, содержащему подробные сведения о сравнении.</span><span class="sxs-lookup"><span data-stu-id="5b368-111">[out] An [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b368-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5b368-112">Return Value</span></span>  
 <span data-ttu-id="5b368-113">`pfEquivalent`Возвращает логическое значение, указывающее, равны ли две сборки.</span><span class="sxs-lookup"><span data-stu-id="5b368-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="5b368-114">`pResult`Возвращает одно из `AssemblyComparisonResult` значений, чтобы предоставить более подробные причину значение `pfEquivalent`.</span><span class="sxs-lookup"><span data-stu-id="5b368-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b368-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b368-115">Remarks</span></span>  
 <span data-ttu-id="5b368-116">`CompareAssemblyIdentity`проверяет, является ли `pwzAssemblyIdentity1` и `pwzAssemblyIdentity2` являются эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="5b368-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="5b368-117">`pfEquivalent`имеет значение `true` в одной или нескольких из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="5b368-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
-   <span data-ttu-id="5b368-118">Идентификаторы двух сборок эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="5b368-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="5b368-119">Для сборок со строгими именами эквивалентности требуется имя сборки, версию, маркер открытого ключа и языка и региональных параметров, считаются идентичными.</span><span class="sxs-lookup"><span data-stu-id="5b368-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="5b368-120">Для сборок с простыми именами эквивалентности требуется совпадение имени сборки и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="5b368-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
-   <span data-ttu-id="5b368-121">Оба идентификатора сборки ссылаются на сборки, выполняемые на платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5b368-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="5b368-122">Это условие возвращает `true` даже если номерах версий сборки не совпадают.</span><span class="sxs-lookup"><span data-stu-id="5b368-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
-   <span data-ttu-id="5b368-123">Обе сборки не являются управляемыми, но `fUnified1` или `fUnified2` было задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5b368-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="5b368-124">`fUnified` Флаг указывает, что все номера версий до номер версии сборки строгим именем эквивалентны к сборке со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="5b368-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="5b368-125">Например если значение `pwzAssemblyIndentity1` — «MyAssembly, версии 3.0.0.0, culture = = neutral, publicKeyToken =...» и значение `fUnified1` — `true`, это означает, что должен быть MyAssembly версии 3.0.0.0 0.0.0.0 для всех версий рассматривается как эквивалент.</span><span class="sxs-lookup"><span data-stu-id="5b368-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="5b368-126">В этом случае если `pwzAssemblyIndentity2` относится к одной сборке с `pwzAssemblyIndentity1`, за исключением того, что ниже номера версии, `pfEquivalent` равно `true`.</span><span class="sxs-lookup"><span data-stu-id="5b368-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="5b368-127">Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии `pfEquivalent` равно `true` только тогда, когда значение `fUnified2` — `true`.</span><span class="sxs-lookup"><span data-stu-id="5b368-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="5b368-128">`pResult` Параметр содержатся особые сведения о том, почему две сборки считаются эквивалентным или не является эквивалентным.</span><span class="sxs-lookup"><span data-stu-id="5b368-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="5b368-129">Дополнительные сведения см. в разделе [перечисление AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="5b368-129">For more information, see [AssemblyComparisonResult Enumeration](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b368-130">Требования</span><span class="sxs-lookup"><span data-stu-id="5b368-130">Requirements</span></span>  
 <span data-ttu-id="5b368-131">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b368-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b368-132">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="5b368-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5b368-133">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b368-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b368-134">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b368-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b368-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5b368-135">See Also</span></span>  
 [<span data-ttu-id="5b368-136">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="5b368-136">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [<span data-ttu-id="5b368-137">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="5b368-137">AssemblyComparisonResult Enumeration</span></span>](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
