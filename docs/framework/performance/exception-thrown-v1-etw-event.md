---
title: Событие ExceptionThrown_V1 (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f0e968053c87319bf90bf3de0f21d750ec899ab
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447627"
---
# <a name="exception-thrown_v1-etw-event"></a>Событие ExceptionThrown_V1 (трассировка событий Windows)
Это событие захватывает информацию о вызванных исключениях.  
  
 В следующей таблице показаны ключевое слово, в котором вызывается событие, и уровень события. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`ExceptionKeyword` (0x8000)|Предупреждение (2)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|80|Возникло управляемое исключение.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|Тип исключения|win:UnicodeString|Тип исключения, например `System.NullReferenceException`.|  
|Сообщение об исключении|win:UnicodeString|Фактическое сообщение об исключении.|  
|EIPCodeThrow|win:Pointer|Указатель на инструкцию, в которой возникло исключение.|  
|ExceptionHR|win:UInt32|Исключение [HRESULT](https://docs.microsoft.com/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).|  
|ExceptionFlags|win:UInt16|0x01: HasInnerException (см. раздел [События трассировки событий Windows в среде CLR](clr-etw-events.md) в документации по Visual Basic).<br /><br /> 0x02: IsNestedException.<br /><br /> 0x04: IsRethrownException.<br /><br /> 0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://docs.microsoft.com/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).<br /><br /> 0x10: IsCLSCompliant (исключение, производное от <xref:System.Exception>, является CLS-совместимым; в противном случае такое исключение не является CLS-совместимым).|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
## <a name="see-also"></a>См. также

- [События трассировки событий Windows в среде CLR](clr-etw-events.md)
