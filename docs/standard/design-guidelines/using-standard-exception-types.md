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
ms.openlocfilehash: 6b202d618d9d2216c8998181303250081de6781c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708988"
---
# <a name="using-standard-exception-types"></a>Использование исключений стандартных типов
В этом разделе описаны стандартные исключения, предоставляемые платформой, и сведения об их использовании. Список не является исчерпывающим. Сведения об использовании других типов исключений платформы см. в справочной документации по .NET Framework.  
  
## <a name="exception-and-systemexception"></a>Exception и SystemException  
 **X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> или <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** перехватывать `System.Exception` или `System.SystemException` в код платформы, если не требуется заново создать.  
  
 **X AVOID** перехват `System.Exception` или `System.SystemException`, за исключением обработчики исключений верхнего уровня.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** throw или являются производными от <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** исключение <xref:System.InvalidOperationException> , если объект находится в недопустимом состоянии.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException и ArgumentOutOfRangeException  
 **✓ DO** throw <xref:System.ArgumentException> или один из его подтипов, если член переданы недопустимые аргументы. Предпочитать наиболее производный тип исключения, если применимо.  
  
 **✓ DO** задать `ParamName` свойство при генерации один подклассы `ArgumentException`.  
  
 Это свойство представляет имя параметра, вызвавшего исключение. Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.  
  
 **✓ DO** использовать `value` для имени неявного параметра значения методов установки свойств.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException и AccessViolationException  
 **X DO NOT** разрешить произвольного API-интерфейсы для явным или неявным образом вызывать <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, или <xref:System.IndexOutOfRangeException>. Эти исключения зарезервированы и создаются подсистемой выполнения и в большинстве случаев указывают на ошибку.  
  
 Проследите за проверкой аргументов, чтобы избежать возникновения этих исключений. Создание этих исключений предоставляет сведения о реализации метода, которые могут меняться со временем.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** явно вызывать <xref:System.StackOverflowException>. Исключение должно быть явно вызвано только средой CLR.  
  
 **X DO NOT** перехватывать `StackOverflowException`.  
  
 Практически невозможно написать управляемый код, который остается единообразным при наличии произвольных переходящих стеков стека. Неуправляемые части среды CLR остаются неизменными с помощью зондов для перемещения передатчиков стека в четко определенные места, а не при резервном копировании из произвольных передатчиков стека.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** явно вызывать <xref:System.OutOfMemoryException>. Это исключение возникает только в инфраструктуре среды CLR.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException, SEHException и ExecutionEngineException  
 **X DO NOT** явно вызывать <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, и <xref:System.Runtime.InteropServices.SEHException>. Эти исключения должны вызываться только инфраструктурой CLR.  
  
 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила разработки исключений](../../../docs/standard/design-guidelines/exceptions.md)
