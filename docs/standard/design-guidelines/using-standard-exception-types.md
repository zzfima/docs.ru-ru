---
title: "Использование исключений стандартных типов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Создание исключений стандартных типов"
  - "перехват исключений"
  - "перехват исключений"
  - "исключения, возникновение"
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Использование исключений стандартных типов
В этом разделе описываются стандартных исключений, предоставляемых Framework и сведения об их использовании. Список отнюдь не является исчерпывающим. См. справочную документацию платформы .NET Framework для использования других типов исключений Framework.  
  
## Исключения и SystemException  
 **X не** исключение <xref:System.Exception?displayProperty=fullName> или <xref:System.SystemException?displayProperty=fullName>.  
  
 **X не** catch `System.Exception` или `System.SystemException` в коде, если не требуется заново создать.  
  
 **ИЗБЕЖАТЬ X** перехват `System.Exception` или `System.SystemException`, за исключением обработчики исключений верхнего уровня.  
  
## ApplicationException  
 **X не** исключение или являются производными от <xref:System.ApplicationException>.  
  
## InvalidOperationException  
 **✓ сделать** исключение <xref:System.InvalidOperationException> если объект находится в недопустимом состоянии.  
  
## ArgumentException ArgumentNullException и ArgumentOutOfRangeException  
 **✓ сделать** исключение <xref:System.ArgumentException> или один из его подтипов, если члену передаются недопустимые аргументы. Предпочтение наиболее производный тип исключения, если это применимо.  
  
 **✓ сделать** задать `ParamName` свойства при генерации один подклассы `ArgumentException`.  
  
 Это свойство представляет имя параметра, вызвавшего исключение. Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.  
  
 **✓ сделать** использовать `value` для имени неявного параметра значения методов установки свойств.  
  
## Исключение NullReferenceException, IndexOutOfRangeException и AccessViolationException  
 **X не** разрешить произвольного API для явным или неявным образом вызывать <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, или <xref:System.IndexOutOfRangeException>. Эти исключения зарезервированы и возникает ядро выполнения, так и в большинстве случаев указывать на ошибку.  
  
 Выполните проверку, чтобы избежать возникновения таких исключений аргументов. Вызов этих исключений предоставляет сведения о реализации метода, которая может изменяться со временем.  
  
## Исключение StackOverflowException  
 **X не** явно вызывать <xref:System.StackOverflowException>. Исключение должно явно вызываться только средой CLR.  
  
 **X не** catch `StackOverflowException`.  
  
 Это почти невозможно написать управляемый код, который остается согласованным при наличии переполнения стека произвольные. Неуправляемые компоненты среды CLR остаются согласованными с помощью зонды перемещать переполнения стека, чтобы четко определенных местах, а не с выхода из переполнения стека произвольных.  
  
## OutOfMemoryException  
 **X не** явно вызывать <xref:System.OutOfMemoryException>. Это исключение вызываться только средой CLR.  
  
## ComException, SEHException и ExecutionEngineException  
 **X не** явно вызывать <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, и <xref:System.Runtime.InteropServices.SEHException>. Эти исключения должны вызываться только средой CLR.  
  
 *Частей © 2005, 2009 корпорации Microsoft. Все права защищены.*  
  
 *Воспроизведены разрешении Пирсон образования, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для повторного использования библиотеки .NET, второе издание](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс опубликованы 22 октября 2008 г., издательство Addison\-Wesley Professional как часть цикла разработки Microsoft Windows.*  
  
## См. также  
 [Рекомендации по проектированию Framework](../../../docs/standard/design-guidelines/index.md)   
 [Правила разработки исключений](../../../docs/standard/design-guidelines/exceptions.md)