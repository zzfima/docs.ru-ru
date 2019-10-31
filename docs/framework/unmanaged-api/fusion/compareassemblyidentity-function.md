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
# <a name="compareassemblyidentity-function"></a>Функция CompareAssemblyIdentity
Сравнивает два идентификатора сборки, чтобы определить, являются ли они эквивалентными.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="parameters"></a>Параметры  
 `pwzAssemblyIdentity1`  
 окне Текстовое удостоверение первой сборки в сравнении.  
  
 `fUnified1`  
 окне Логический флаг, указывающий, что для `pwzAssemblyIdentity1`указана пользовательская унификация.  
  
 `pwzAssemblyIdentity2`  
 окне Текстовое удостоверение второй сборки в сравнении.  
  
 `fUnified2`  
 окне Логический флаг, указывающий, что для `pwzAssemblyIdentity2`указана пользовательская унификация.  
  
 `pfEquivalent`  
 заполняет Логический флаг, указывающий, эквивалентны ли две сборки.  
  
 `pResult`  
 заполняет Перечисление [ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md) , содержащее подробные сведения о сравнении.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `pfEquivalent` возвращает логическое значение, указывающее, эквивалентны ли две сборки. `pResult` возвращает одно из значений `AssemblyComparisonResult`, чтобы получить более подробную причину для значения `pfEquivalent`.  
  
## <a name="remarks"></a>Заметки  
 `CompareAssemblyIdentity` проверяет, эквивалентны ли `pwzAssemblyIdentity1` и `pwzAssemblyIdentity2`. `pfEquivalent` имеет значение `true` в одном или нескольких из следующих условий:  
  
- Два удостоверения сборки эквивалентны. Для строго именованных сборок эквивалентность требует идентичности имени сборки, версии, токена открытого ключа и языка и региональных параметров. Для просто именованных сборок эквивалентность требует соответствия имени сборки и языку и региональным параметрам.  
  
- Оба удостоверения сборки ссылаются на сборки, которые выполняются в .NET Framework. Это условие возвращает `true` даже в том случае, если номера версий сборки не совпадают.  
  
- Эти две сборки не являются управляемыми сборками, но для `fUnified1` или `fUnified2` задано значение `true`.  
  
 Флаг `fUnified` указывает, что все номера версий, вплоть до номера версии строго именованной сборки, считаются эквивалентными строго именованной сборке. Например, если значение `pwzAssemblyIndentity1` равно "MyAssembly, Version = 3.0.0.0, культура = Neutral, publicKeyToken =....", а значение `fUnified1` — `true`, это означает, что все версии MyAssembly из версии 0.0.0.0 в 3.0.0.0 должны рассматриваться как друг. В этом случае, если `pwzAssemblyIndentity2` ссылается на ту же сборку, что и `pwzAssemblyIndentity1`, за исключением того, что имеет меньший номер версии, `pfEquivalent` устанавливается в `true`. Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии, `pfEquivalent` устанавливается в `true` только в том случае, если `fUnified2` имеет значение `true`.  
  
 Параметр `pResult` содержит конкретные сведения о том, почему две сборки считаются эквивалентными или не эквивалентными. Дополнительные сведения см. в разделе [перечисление ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
- [Перечисление AssemblyComparisonResult](assemblycomparisonresult-enumeration.md)
