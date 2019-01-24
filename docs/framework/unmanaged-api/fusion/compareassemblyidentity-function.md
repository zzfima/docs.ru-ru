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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a523a58a137f8276df854da956b3ab0b75cbcec9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571630"
---
# <a name="compareassemblyidentity-function"></a>Функция CompareAssemblyIdentity
Сравнивает два идентификатора сборки, чтобы определить, являются ли они равными.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pwzAssemblyIdentity1`  
 [in] Текстовым идентификатором первой сборки в сравнении.  
  
 `fUnified1`  
 [in] Логический флаг, указывающий пользовательские унификацию для `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] Текстовый идентификатор вторую сборку для сравнения.  
  
 `fUnified2`  
 [in] Логический флаг, указывающий пользовательские унификацию для `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Логический флаг, указывающее, равны ли две сборки.  
  
 `pResult`  
 [out] [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) перечислению, содержащему подробные сведения о сравнении.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `pfEquivalent` Возвращает логическое значение, указывающее, равны ли две сборки. `pResult` Возвращает одно из `AssemblyComparisonResult` значений, чтобы предоставить более подробные причину значение `pfEquivalent`.  
  
## <a name="remarks"></a>Примечания  
 `CompareAssemblyIdentity` проверяет ли `pwzAssemblyIdentity1` и `pwzAssemblyIdentity2` эквивалентны. `pfEquivalent` имеет значение `true` в одной или нескольких из следующих условий:  
  
-   Идентификаторы двух сборок эквивалентны. Для сборок со строгими именами эквивалентности требуется имя сборки, версия, токен открытого ключа и языка и региональных параметров, считаются идентичными. Для сборок с простыми именами эквивалентности требуется сопоставление по имени сборки и языка и региональных параметров.  
  
-   Оба идентификатора сборки ссылаются на сборки, которые выполняются в .NET Framework. Это условие возвращает `true` даже если номера версий сборки не совпадают.  
  
-   Две сборки не являются управляемыми, но `fUnified1` или `fUnified2` было присвоено `true`.  
  
 `fUnified` Флаг указывает, что все номера версий до номер версии сборки со строгими именами, считаются эквивалентными сборкой со строгим именем. К примеру Если значение `pwzAssemblyIndentity1` является «MyAssembly, версии = 3.0.0.0, culture = neutral, publicKeyToken =...» и значение `fUnified1` является `true`, это означает, что должно быть MyAssembly из версии 3.0.0.0 0.0.0.0 для всех версий рассматривается как эквивалент. В этом случае если `pwzAssemblyIndentity2` ссылается на ту же сборку `pwzAssemblyIndentity1`, за исключением того, что ниже номера версии, `pfEquivalent` присваивается `true`. Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии `pfEquivalent` присваивается `true` только если значение `fUnified2` является `true`.  
  
 `pResult` Параметр содержит определенные сведения о почему две сборки считаются эквивалентным или не является эквивалентным. Дополнительные сведения см. в разделе [перечисление AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [Перечисление AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
