---
title: Перечисление AssemblyComparisonResult
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: e3cdb648397ca4f4aa2326e4f2349a5a14c3edcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178294"
---
# <a name="assemblycomparisonresult-enumeration"></a>Перечисление AssemblyComparisonResult
Указывает эквивалентность двух идентификаторов сборки, определяемых функцией [CompareAssemblyIdentity.](compareassemblyidentity-function.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Члены  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Означает, что все поля сборки в сравнении.|  
|`ACR_EquivalentFXUnified`|Указывается, что сборки считаются эквивалентными на основе общей версии выполнения языка (CLR) унификации номеров сборочной версии в версии .NET Framework 2.0.|  
|`ACR_EquivalentPartialFXUnified`|Указывает частичное совпадение сборок на основе объединения номеров сборочной версии CLR в .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Указывает частичное совпадение сборок.|  
|`ACR_EquivalentPartialUnified`|Указывает частичное совпадение сборок на основе устаревшего объединения номеров версий.|  
|`ACR_EquivalentPartialWeakNamed`|Указывает частичное совпадение просто названных сборок.|  
|`ACR_EquivalentUnified`|Указывает, что сборки считаются эквивалентными на основе объединения номеров версий CLR в устаревших версиях рамочной программы .NET.|  
|`ACR_EquivalentWeakNamed`|Указывает на совпадение между двумя просто названными сборками, номера версий которых были проигнорированы.|  
|`ACR_NonEquivalent`|Указывает на то, что между двумя сборками не произошло совпадений.|  
|`ACR_NonEquivalentPartialVersion`|Означает, что две сборки совпадают, за исключением их номеров версий, которые совпадают лишь частично.|  
|`ACR_NonEquivalentVersion`|Означает, что две сборки совпадают, за исключением их номеров версий, которые не совпадают.|  
|`ACR_Unknown`|Указывает на то, что причина неэквивалентности неизвестна.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CompareAssemblyIdentity](compareassemblyidentity-function.md)
- [Перечисления Fusion](fusion-enumerations.md)
