---
title: События трассировки JIT-компилятора (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT tracing events [.NET Framework]
- ETW, JIT tracing events (CLR)
ms.assetid: 926adde2-c123-452e-bf4f-4b977bf06ffb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4daa0fc0d689815e3a2c65df09c6c046d06a25c4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975501"
---
# <a name="jit-tracing-etw-events"></a>События трассировки JIT-компилятора (трассировка событий Windows)
Эти события собирают сведения, относящиеся к успешному или неудачному встраиванию кода JIT и вызовам с префиксом tail в JIT.

## <a name="jit-inlining-events"></a>События встраивания кода JIT

### <a name="methodjitinliningfailed-event"></a>Событие MethodJitInliningFailed
 В таблице ниже показаны ключевое слово и уровень. (Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Подробный (5)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`MethodJitInliningFailed`|186|Встраивание кода JIT не удалось.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Пространство имен компилируемого метода.|  
|MethodBeingCompiledName|win:UnicodeString|Имя компилируемого метода.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Сигнатура компилируемого метода.|  
|InlinerNamespace|win:UnicodeString|Пространство имен метода, для которого JIT-компилятор пытается создать код.|  
|InlinerName|win:UnicodeString|Имя метода, для которого компилятор пытается создать код. Может отличаться от `MethodBeingCompiledName` , если компилятор пытается встроить код в `MethodBeingCompiledName` вместо создания вызова `InlinerName`.|  
|InlinerNameSignature|win:UnicodeString|Сигнатура для метода встраивания.|  
|InlineeNamespace|win:UnicodeString|Пространство имен встраиваемого метода.|  
|InlineeName|win:UnicodeString|Метод, который компилятор пытается встроить (а не создать для него вызов).|  
|InlineeNameSignature|win:UnicodeString|Сигнатура для встраиваемого метода.|  
|FailAlways|win:Boolean|Подсказка JIT-компилятору, что встраивание этого метода всегда будет заканчиваться неудачей.|  
|FailReason|win:UnicodeString|INLINE_NEVER означает, что предыдущая попытка встраивания кода определила, что встраивание по какой-то причине никогда не закончится успехом; в противном случае — текст в свободной форме.|  
|ClrInstanceID|win:UnicodeString|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
### <a name="methodjitinliningsucceeded-event"></a>Событие MethodJitInliningSucceeded  
 В таблице ниже показаны ключевое слово и уровень.  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Подробный (5)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`MethodJitInliningSucceeded`|185|Встраивание метода выполнено успешно.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Пространство имен компилируемого метода.|  
|MethodBeingCompiledName|win:UnicodeString|Имя компилируемого метода.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Сигнатура компилируемого метода.|  
|InlinerNamespace|win:UnicodeString|Пространство имен метода, для которого JIT-компилятор пытается создать код.|  
|InlinerName|win:UnicodeString|Имя метода, для которого компилятор пытается создать код. Может отличаться от `MethodBeingCompiledName` , если компилятор пытается встроить код в `MethodBeingCompiledName` вместо создания вызова `InlinerName`.|  
|InlinerNameSignature|win:UnicodeString|Сигнатура для метода встраивания.|  
|InlineeNamespace|win:UnicodeString|Пространство имен встраиваемого метода.|  
|InlineeName|win:UnicodeString|Метод, который компилятор пытается встроить (а не создать для него вызов).|  
|InlineeNameSignature|win:UnicodeString|Сигнатура для встраиваемого метода.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  

## <a name="jit-tail-call-events"></a>События вызовов с префиксом tail в JIT  
  
### <a name="methodjittailcallfailed-event"></a>Событие MethodJITTailCallFailed  
 В таблице ниже показаны ключевое слово и уровень.  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Подробный (5)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`MethodJitTailCallFailed`|189|Сбой вызова метода с префиксом tail.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Пространство имен компилируемого метода.|  
|MethodBeingCompiledName|win:UnicodeString|Имя компилируемого метода.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Сигнатура компилируемого метода.|  
|CallerNamespace|win:UnicodeString|Пространство имен метода, для которого JIT-компилятор пытается создать код.|  
|CallerName|win:UnicodeString|Имя метода, для которого компилятор пытается создать код.|  
|CallerNameSignature|win:UnicodeString|Сигнатура для вызывающего объекта.|  
|CalleeNamespace|win:UnicodeString|Пространство имен для вызываемого метода.|  
|CalleeName|win:UnicodeString|Метод, который компилятор пытается вызвать с префиксом tail (а не создать для него вызов).|  
|CalleeNameSignature|win:UnicodeString|Сигнатура для вызываемого метода.|  
|TailPrefix|win:Boolean|Префикс для вызова с префиксом tail.|  
|FailReason|win:UnicodeString|Причина сбоя вызова с префиксом tail.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
### <a name="methodjittailcallsucceeded-event"></a>Событие MethodJITTailCallSucceeded  
 В таблице ниже показаны ключевое слово и уровень.  
  
|Ключевое слово для вызова события|Уровень|  
|-----------------------------------|-----------|  
|`JITTracingKeyword` (0x10)|Подробный (5)|  
  
 В таблице ниже представлены сведения о событии.  
  
|событие|Код события|Условие вызова|  
|-----------|--------------|-----------------|  
|`MethodJitTailCallSucceeded`|188|Успешное завершение вызова метода с префиксом tail.|  
  
 В таблице ниже представлены данные события.  
  
|Имя поля|Тип данных|Описание|  
|----------------|---------------|-----------------|  
|MethodBeingCompiledNameSpace|win:UnicodeString|Пространство имен компилируемого метода.|  
|MethodBeingCompiledName|win:UnicodeString|Имя компилируемого метода.|  
|MethodBeingCompiledNameSignature|win:UnicodeString|Сигнатура компилируемого метода.|  
|CallerNamespace|win:UnicodeString|Пространство имен метода, для которого JIT-компилятор пытается создать код.|  
|CallerName|win:UnicodeString|Имя метода, для которого компилятор пытается создать код.|  
|CallerNameSignature|win:UnicodeString|Сигнатура для вызывающего объекта.|  
|CalleeNamespace|win:UnicodeString|Пространство имен для вызываемого метода.|  
|CalleeName|win:UnicodeString|Метод, который компилятор пытается вызвать с префиксом tail (а не создать для него вызов).|  
|CalleeNameSignature|win:UnicodeString|Сигнатура для вызываемого метода.|  
|TailPrefix|win:Boolean|Префикс для вызова с префиксом tail.|  
|TailCallType|win:UnicodeString|Тип вызова с префиксом tail.|  
|ClrInstanceID|win:UInt16|Уникальный идентификатор экземпляра CLR или CoreCLR.|  
  
## <a name="see-also"></a>См. также

- [События трассировки событий Windows в среде CLR](clr-etw-events.md)
