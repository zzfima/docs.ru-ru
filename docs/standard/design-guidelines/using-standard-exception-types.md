---
title: Использование исключений стандартных типов
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81e4047c171e3a58f335821d64390432524b25df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-standard-exception-types"></a>Использование исключений стандартных типов
В этом разделе описываются стандартных исключений, предоставляемых средой .NET Framework и сведения об их использования. Список не является полным. Обратитесь к справочной документации .NET Framework для использования других типов исключений Framework.  
  
## <a name="exception-and-systemexception"></a>Исключения и SystemException  
 **X не** throw <xref:System.Exception?displayProperty=nameWithType> или <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X не** перехватывать `System.Exception` или `System.SystemException` в код платформы, если не требуется заново создать.  
  
 **X ИЗБЕГАЙТЕ** перехват `System.Exception` или `System.SystemException`, за исключением обработчики исключений верхнего уровня.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X не** throw или являются производными от <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **СДЕЛАТЬ ✓** исключение <xref:System.InvalidOperationException> , если объект находится в недопустимом состоянии.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException ArgumentNullException и ArgumentOutOfRangeException  
 **СДЕЛАТЬ ✓** throw <xref:System.ArgumentException> или один из его подтипов, если член переданы недопустимые аргументы. Предпочтительно наиболее производный тип исключения, если это применимо.  
  
 **СДЕЛАТЬ ✓** задать `ParamName` свойство при генерации один подклассы `ArgumentException`.  
  
 Это свойство представляет имя параметра, вызвавшего исключение. Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.  
  
 **СДЕЛАТЬ ✓** использовать `value` для имени неявного параметра значения методов установки свойств.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>Исключение NullReferenceException, IndexOutOfRangeException и AccessViolationException  
 **X не** разрешить произвольного API-интерфейсы для явным или неявным образом вызывать <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, или <xref:System.IndexOutOfRangeException>. Эти исключения резервируются и вызывается подсистемой выполнения, так и в большинстве случаев указывать на ошибку.  
  
 Выполните проверку, чтобы избежать возникновения этих исключений аргументов. Вызов этих исключений предоставляет сведения о реализации метода, могут измениться с течением времени.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X не** явно вызывать <xref:System.StackOverflowException>. Это исключение должно явно вызываться только средой CLR.  
  
 **X не** перехватывать `StackOverflowException`.  
  
 Это было практически невозможно для написания управляемого кода, который остается согласованным при наличии переполнение стека произвольные. Неуправляемые компоненты среды CLR остаются согласованными с помощью зондов перемещать переполнения стека в четко определенных местах, а не по выхода из переполнение стека произвольные.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X не** явно вызывать <xref:System.OutOfMemoryException>. Это исключение не должны вызываться только средой CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException SEHException и ExecutionEngineException  
 **X не** явно вызывать <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, и <xref:System.Runtime.InteropServices.SEHException>. Эти исключения должны вызываться только средой CLR.  
  
 *Фрагменты © 2005, 2009 корпорации Майкрософт. Все права защищены.*  
  
 *Перепечатываются разрешении Пирсона для образовательных учреждений, Inc. из [Framework рекомендации по проектированию: условные обозначения, стили и шаблоны для библиотеки .NET для повторного использования, 2-е издание](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina и Брэд Абрамс, опубликованные 22 октября 2008 г., Addison-Wesley Professional в составе ряда разработки Microsoft Windows.*  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
 [Правила разработки исключений](../../../docs/standard/design-guidelines/exceptions.md)
