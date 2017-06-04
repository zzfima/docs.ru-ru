---
title: "Атрибут GUID_ManagedName | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "GUID_ManagedName"
apilocation: 
  - "alink.dll"
apitype: "COM"
f1_keywords: 
  - "GUID_ManagedName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID_ManagedName - атрибут"
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Атрибут GUID_ManagedName
Определяет пользовательский интерфейс, который задает имя управляемого пространства имен для библиотеки компонентов объекта модели \(COM\).  
  
## Синтаксис  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### Параметры  
 `value`  
 Имя управляемого пространства имен для библиотеки.  
  
## Определение  
 `GUID_ManagedName` определяется в Cor.h следующим образом:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## Заметки  
 Настраиваемый атрибут интерфейса определяет метаданные для объекта в библиотеке типов.  
  
 Используйте <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=fullName> или <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=fullName> для получения управляемое имя из атрибута.  
  
 Дополнительные сведения см. в разделе [Interface Attributes](../Topic/Interface%20Attributes.md) в Visual C\+\+ справочной документации.  
  
## Пример  
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
  
## Требования  
 **Заголовок:** Cor.h