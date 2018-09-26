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
ms.openlocfilehash: 9ea4a61be3a76c30c564cbf98ba3318fc6c3e7d4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216100"
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
  
## <a name="stackoverflowexception"></a>Исключение StackOverflowException  
 **X DO NOT** явно вызывать <xref:System.StackOverflowException>. Исключение должно явно вызываться только средой CLR.  
  
 **X DO NOT** перехватывать `StackOverflowException`.  
  
 Это почти невозможно написать управляемый код, который остается согласованным при наличии переполнения стека произвольные. Неуправляемые компоненты CLR остаются согласованными, с помощью проверок для перемещения переполнения стека, чтобы четко определенных местах, а не путем выхода из переполнения стека произвольные.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** явно вызывать <xref:System.OutOfMemoryException>. Это исключение не должны вызываться только средой CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException SEHException и ExecutionEngineException  
 **X DO NOT** явно вызывать <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, и <xref:System.Runtime.InteropServices.SEHException>. Эти исключения должны вызываться только средой CLR.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
- [Правила разработки исключений](../../../docs/standard/design-guidelines/exceptions.md)
