---
title: События сведений времени выполнения (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- runtime information events [.NET Framework]
- ETW, runtime information events
ms.assetid: 68b4edbc-7f3b-45f6-ab75-4fd066d6af9a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af27ddaa69d34976929f40055bc2cc668f877e87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117408"
---
# <a name="runtime-information-etw-events"></a>События сведений времени выполнения (трассировка событий Windows)
Эти события трассировки событий Windows регистрируют информацию о среде выполнения, включая SKU, номер версии, способ активизации среды выполнения, параметры командной строки при ее запуске, GUID (если применимо) и другие релевантные данные. Если в процессе выполняется одновременно несколько сред выполнения, в этих событиях предоставляются сведения (ClrInstanceID), которые позволяют однозначно определить нужную среду.  
  
 В таблице ниже представлены два события со сведениями о среде выполнения. Эти события могут вызываться с любым ключевым словом или маской. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|событие|Идентификатор события|Поставщик|Описание|  
|-----------|--------------|--------------|-----------------|  
|`RuntimeInformationEvent`|187|CLRRuntime|Вызывается при загрузке среды выполнения.|  
|`RuntimeInformationDCStart`|187|CLRRundown|Перечисляет загруженные среды выполнения.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
|Sku|win:UInt16|1 — Desktop CLR.<br /><br /> 2 — CoreCLR.|  
|BclVersion — основной номер версии|win:UInt16|Основной номер версии библиотеки mscorlib.dll.|  
|BclVersion — дополнительный номер версии|win:UInt16|Дополнительный номер версии библиотеки mscorlib.dll.|  
|BclVersion — номер сборки|win:UInt16|Номер сборки библиотеки mscorlib.dll.|  
|BclVersion — QFE|win:UInt16|Номер версии исправления библиотеки mscorlib.dll.|  
|VMVersion — основной номер версии|win:UInt16|Версия clr.dll или coreclr.dll в зависимости от номера SKU.|  
|VMVersion — дополнительный номер версии|win:UInt16|Дополнительный номер версии clr.dll или coreclr.dll в зависимости от номера SKU.|  
|VMVersion — номер сборки|win:UInt16|Номер сборки библиотеки clr.dll или coreclr.dll.|  
|VMVersion — QFE|win:UInt16|Номер исправления библиотеки clr.dll или coreclr.dll.|  
|StartupFlags|win:UInt32|Флаги загрузки, определенные в mscoree.h.|  
|StartupMode|win:UInt8|0x01 — управляемый исполняемый файл.<br /><br /> 0x02 — размещенная среда CLR.<br /><br /> 0x04 — управляемая модель взаимодействия C++.<br /><br /> 0x08 — активация COM.<br /><br /> 0x10 — другое.|  
|CommandLine|win:UnicodeString|Отличное от NULL значение только для StartupMode=0x01.|  
|ComObjectGUID|win:GUID|Отличное от NULL значение только для StartupMode=0x08.|  
|RuntimeDLLPath|win:UnicodeString|Путь к DLL-файлу среды CLR, который был загружен в процесс.|  
  
## <a name="see-also"></a>См. также

- [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)
