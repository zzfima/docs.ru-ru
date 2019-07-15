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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6c417eec9583ff069c9d61fa31e9c14f3931130
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778506"
---
# <a name="assemblycomparisonresult-enumeration"></a>Перечисление AssemblyComparisonResult
Эквивалентность двух идентификаторов сборок, указывает, что определяется [CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md) функции.  
  
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
  
## <a name="members"></a>Участники  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Указывает, что все поля сборки в соответствие сравнения.|  
|`ACR_EquivalentFXUnified`|Указывает, что сборки эквивалентны на основе общих унификации версию (CLR) среды выполнения языка для номеров версии сборок в .NET Framework версии 2.0.|  
|`ACR_EquivalentPartialFXUnified`|Указывает на частичное совпадение сборок на основе унификации среды CLR для номеров версии сборок в .NET Framework 2.0.|  
|`ACR_EquivalentPartialMatch`|Указывает на частичное совпадение сборок.|  
|`ACR_EquivalentPartialUnified`|Указывает на частичное совпадение сборок, на основе предыдущих версий унификации для номера версий.|  
|`ACR_EquivalentPartialWeakNamed`|Указывает на частичное совпадение простым именем сборки.|  
|`ACR_EquivalentUnified`|Указывает, что сборки эквивалентны на основе унификации CLR для номера версий в прежних версиях платформы .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Указывает соответствие между две простым именем сборки, номера версий были пропущены.|  
|`ACR_NonEquivalent`|Указывает, что совершенно не совпадают две сборки.|  
|`ACR_NonEquivalentPartialVersion`|Указывает совпадение двух сборок, за исключением номеров версии, которые соответствуют только частично.|  
|`ACR_NonEquivalentVersion`|Указывает совпадение двух сборок, за исключением номеров версии, которые не совпадают.|  
|`ACR_Unknown`|Указывает, что причина неравенства не известна.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CompareAssemblyIdentity](../../../../docs/framework/unmanaged-api/fusion/compareassemblyidentity-function.md)
- [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
