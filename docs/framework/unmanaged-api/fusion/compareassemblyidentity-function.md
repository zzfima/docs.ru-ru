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
ms.openlocfilehash: 1b48adcb8e9de49a312af77c8a9b80a07455ebfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compareassemblyidentity-function"></a>Функция CompareAssemblyIdentity
Сравнивает два идентификатора сборки, чтобы определить, эквивалентны ли они.  
  
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
 [in] Логический флаг, который указывает определяемый пользователем унификацию для `pwzAssemblyIdentity1`.  
  
 `pwzAssemblyIdentity2`  
 [in] Текстовым идентификатором вторую сборку для сравнения.  
  
 `fUnified2`  
 [in] Логический флаг, который указывает определяемый пользователем унификацию для `pwzAssemblyIdentity2`.  
  
 `pfEquivalent`  
 [out] Логический флаг, указывающее, равны ли две сборки.  
  
 `pResult`  
 [out] [AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md) перечисления, содержащему подробные сведения о сравнении.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `pfEquivalent` Возвращает логическое значение, указывающее, равны ли две сборки. `pResult` Возвращает одно из `AssemblyComparisonResult` значений, чтобы предоставить более подробные причину значение `pfEquivalent`.  
  
## <a name="remarks"></a>Примечания  
 `CompareAssemblyIdentity` проверяет, является ли `pwzAssemblyIdentity1` и `pwzAssemblyIdentity2` являются эквивалентными. `pfEquivalent` имеет значение `true` в одной или нескольких из следующих условий:  
  
-   Идентификаторы двух сборок эквивалентны. Для сборок со строгими именами эквивалентности требуется имя сборки, версию, маркер открытого ключа и языка и региональных параметров, считаются идентичными. Для сборок с простыми именами эквивалентности требуется совпадение имени сборки и языка и региональных параметров.  
  
-   Оба идентификатора сборки ссылаются на сборки, выполняемые на платформе .NET Framework. Это условие возвращает `true` даже если номерах версий сборки не совпадают.  
  
-   Обе сборки не являются управляемыми, но `fUnified1` или `fUnified2` было задано значение `true`.  
  
 `fUnified` Флаг указывает, что все номера версий до номер версии сборки строгим именем эквивалентны к сборке со строгим именем. Например если значение `pwzAssemblyIndentity1` — «MyAssembly, версии 3.0.0.0, culture = = neutral, publicKeyToken =...» и значение `fUnified1` — `true`, это означает, что должен быть MyAssembly версии 3.0.0.0 0.0.0.0 для всех версий рассматривается как эквивалент. В этом случае если `pwzAssemblyIndentity2` относится к одной сборке с `pwzAssemblyIndentity1`, за исключением того, что ниже номера версии, `pfEquivalent` равно `true`. Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии `pfEquivalent` равно `true` только тогда, когда значение `fUnified2` — `true`.  
  
 `pResult` Параметр содержатся особые сведения о том, почему две сборки считаются эквивалентным или не является эквивалентным. Дополнительные сведения см. в разделе [перечисление AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Библиотека:** включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [Перечисление AssemblyComparisonResult](../../../../docs/framework/unmanaged-api/fusion/assemblycomparisonresult-enumeration.md)
