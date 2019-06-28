---
title: События взаимодействия (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c52c9bf37e67e4d26867d2b3754945e86e2bf609
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422414"
---
# <a name="interop-etw-events"></a>События взаимодействия (трассировка событий Windows)
<a name="top"></a> С помощью событий взаимодействия регистрируются сведения о создании заглушек и кэшировании MSIL.  
  
 Эта категория состоит из следующих событий:  
  
- [Событие ILStubGenerated](#ilstubgenerated_event)  
  
- [Событие ILStubCacheHit](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a>Событие ILStubGenerated  
 В таблице ниже показаны ключевое слово и уровень. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Идентификатор события|Условие вызова|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|88|Была создана заглушка языка MSIL.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Идентификатор модуля.|  
|StubMethodID|win:UInt64|Идентификатор метода-заглушки.|  
|StubFlags|win:UInt64|Флаги для заглушки:<br /><br /> 0x1 — обратное взаимодействие;<br /><br /> 0x2 — COM-взаимодействие;<br /><br /> 0x4 — заглушка, созданная программой NGen.exe;<br /><br /> 0x8 — делегат;<br /><br /> 0x10 — переменный аргумент.<br /><br /> 0x20 — неуправляемый вызываемый метод.|  
|ManagedInteropMethodToken|win:UInt32|Токен управляемого метода взаимодействия.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Пространство имен управляемого метода взаимодействия.|  
|ManagedInteropMethodName|win:UnicodeString|Имя управляемого метода взаимодействия.|  
|ManagedInteropMethodSignature|win:UnicodeString|Сигнатура управляемого метода взаимодействия.|  
|NativeMethodSignature|win:UnicodeString|Сигнатура неуправляемого метода.|  
|StubMethodSignature|win:UnicodeString|Сигнатура метода-заглушки.|  
|StubMethodILCode|win:UnicodeString|Код MSIL для метода-заглушки.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
 [К началу](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a>Событие ILStubCacheHit  
 В таблице ниже показаны ключевое слово и уровень.  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Информационный (4)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Идентификатор события|Условие вызова|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|89|Обращение к кэшу MSIL.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Идентификатор модуля.|  
|StubMethodID|win:UInt64|Идентификатор метода-заглушки.|  
|ManagedInteropMethodToken|win:UInt32|Токен управляемого метода взаимодействия.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Пространство имен управляемого метода взаимодействия.|  
|ManagedInteropMethodName|win:UnicodeString|Имя управляемого метода взаимодействия.|  
|ManagedInteropMethodSignature|win:UnicodeString|Сигнатура управляемого метода взаимодействия.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
 [К началу](#top)  
  
## <a name="see-also"></a>См. также

- [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)
