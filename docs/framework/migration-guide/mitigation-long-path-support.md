---
title: "Устранение рисков. Поддержка длинных путей | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 40b4b94ac3058dda88b44c82110d4c749566e2b2
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-long-path-support"></a>Устранение рисков. Поддержка длинных путей
Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], методы ввода-вывода файловой системы не будут автоматически создавать исключение <xref:System.IO.PathTooLongException>, когда длина пути или полного имени файла превышает 260 (или `MAX_PATH`) символов. Вместо этого поддерживаются длинные пути до 32 тыс. символов.  
  
## <a name="impact"></a>Последствия  
 Приложения, перекомпилированные для нацеливания на платформу [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], которые ранее автоматически создавали исключение <xref:System.IO.PathTooLongException>, когда длина пути превышает 260 символов, теперь будут создавать <xref:System.IO.PathTooLongException> только при выполнении следующих условий:  
  
-   Длина пути превышает <xref:System.Int16.MaxValue?displayProperty=fullName> (32 767) символов.  
  
-   операционная система возвращает `COR_E_PATHTOOLONG` или его эквивалент;  
  
 Для приложений, нацеливаемых на [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранние версии, сохраняется прежнее поведение, то есть среда выполнения автоматически создает исключение <xref:System.IO.PathTooLongException> всякий раз, когда длина пути превышает 260 символов.  
  
## <a name="mitigation"></a>Уменьшение  
 Для приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], можно отказаться от поддержки длинных путей, если это нежелательно, добавив следующую строку в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 Для приложений, которые предназначены для более ранних версий .NET Framework, но выполняются в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, можно включить поддержку длинных путей, добавив следующую строку в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

