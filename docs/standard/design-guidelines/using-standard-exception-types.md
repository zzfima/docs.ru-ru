---
title: Использование исключений стандартных типов
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: KrzysztofCwalina
ms.openlocfilehash: b947c7cce057c060b1ab5054d1227f5703ccbf89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026345"
---
# <a name="using-standard-exception-types"></a>Использование исключений стандартных типов
В этом разделе описываются стандартные исключения, предоставляемые платформой и особенностей их использования. Список отнюдь не является исчерпывающим. Обратитесь к документации .NET Framework для использования другие типы исключений платформы.  
  
## <a name="exception-and-systemexception"></a>Исключение и SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> или <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** перехватывать `System.Exception` или `System.SystemException` в код платформы, если не требуется заново создать.  
  
 **X AVOID** перехват `System.Exception` или `System.SystemException`, за исключением обработчики исключений верхнего уровня.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw или являются производными от <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** исключение <xref:System.InvalidOperationException> , если объект находится в недопустимом состоянии.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException и ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> или один из его подтипов, если член переданы недопустимые аргументы. Предпочитаете наиболее производный тип исключения, если это применимо.  
  
 **✓ DO** задать `ParamName` свойство при генерации один подклассы `ArgumentException`.  
  
 Это свойство представляет имя параметра, вызвавшего исключение. Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.  
  
 **✓ DO** использовать `value` для имени неявного параметра значения методов установки свойств.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>Исключение NullReferenceException, IndexOutOfRangeException и AccessViolationException  
 **X DO NOT** разрешить произвольного API-интерфейсы для явным или неявным образом вызывать <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, или <xref:System.IndexOutOfRangeException>. Эти исключения зарезервированы и исключение подсистемой выполнения, так и в большинстве случаев указывать на ошибку.  
  
 Выполните проверку, чтобы избежать возникновения этих исключений аргументов. Эти исключения предоставляет сведения о реализации метода, могут измениться с течением времени.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** явно вызывать <xref:System.StackOverflowException>. Исключение должно явно вызываться только средой CLR.  
  
 **X DO NOT** перехватывать `StackOverflowException`.  
  
 Это почти невозможно написать управляемый код, который остается согласованным при наличии переполнения стека произвольные. Неуправляемые компоненты CLR остаются согласованными, с помощью проверок для перемещения переполнения стека, чтобы четко определенных местах, а не путем выхода из переполнения стека произвольные.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** явно вызывать <xref:System.OutOfMemoryException>. Это исключение не должны вызываться только средой CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException SEHException и ExecutionEngineException  
 **X DO NOT** явно вызывать <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, и <xref:System.Runtime.InteropServices.SEHException>. Эти исключения должны вызываться только средой CLR.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано разрешением Пирсона для образовательных учреждений, Inc. из [рекомендации по разработке Framework: Условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Кшиштов Квалина и Брэд Абрамс, опубликованных 22 октября 2008 г., издательство Addison-Wesley Professional как части цикла разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила разработки исключений](../../../docs/standard/design-guidelines/exceptions.md)
