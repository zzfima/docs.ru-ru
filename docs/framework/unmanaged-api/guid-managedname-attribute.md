---
title: "Атрибут GUID_ManagedName"
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
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 116a9e38b9885f0d0a5afc8f4915b9ce2b50f1dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="guidmanagedname-attribute"></a>Атрибут GUID_ManagedName
Определяет настраиваемый атрибут интерфейса, указывающее имя управляемого пространства имен для библиотеки COM-модели объектов компонента.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### <a name="parameters"></a>Параметры  
 `value`  
 Имя управляемого пространства имен для библиотеки.  
  
## <a name="definition"></a>Определение  
 `GUID_ManagedName`определяется в Cor.h следующим образом:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a>Примечания  
 Настраиваемый атрибут интерфейса определяет метаданные для объекта в библиотеке типов.  
  
 Используйте <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> или <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> получить имя управляемого из атрибута.  
  
 Дополнительные сведения см. в разделе [атрибуты интерфейса](/cpp/windows/interface-attributes) в Visual C++ справочной документации.  
  
## <a name="example"></a>Пример  
 В следующем примере показано определение библиотеки с помощью `GUID_ManagedName` атрибута.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Cor.h
