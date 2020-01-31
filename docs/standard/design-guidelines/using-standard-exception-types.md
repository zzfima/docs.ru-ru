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
ms.openlocfilehash: 3caa94d9a39966614161e4b19201dcf6065776a2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743542"
---
# <a name="using-standard-exception-types"></a>Использование исключений стандартных типов
В этом разделе описаны стандартные исключения, предоставляемые платформой, и сведения об их использовании. Список не является исчерпывающим. Сведения об использовании других типов исключений платформы см. в справочной документации по .NET Framework.

## <a name="exception-and-systemexception"></a>Exception и SystemException
 ❌ не вызывайте <xref:System.Exception?displayProperty=nameWithType> или <xref:System.SystemException?displayProperty=nameWithType>.

 ❌ не перехватывайте `System.Exception` или `System.SystemException` в коде платформы, если не планируется повторный вызов.

 ❌ избежать перехвата `System.Exception` или `System.SystemException`, за исключением обработчиков исключений верхнего уровня.

## <a name="applicationexception"></a>ApplicationException
 ❌ не вызывайте и не наследует от <xref:System.ApplicationException>.

## <a name="invalidoperationexception"></a>InvalidOperationException
 ✔️ выдавать <xref:System.InvalidOperationException>, если объект находится в недопустимом состоянии.

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException, ArgumentNullException и ArgumentOutOfRangeException
 ✔️ Вызывайте <xref:System.ArgumentException> или один из его подтипов, если элементу передаются неверные аргументы. Предпочитать наиболее производный тип исключения, если применимо.

 ✔️ задать свойство `ParamName` при вызове одного из подклассов `ArgumentException`.

 Это свойство представляет имя параметра, вызвавшего исключение. Обратите внимание, что свойство можно задать с помощью одной из перегрузок конструктора.

 ✔️ использовать `value` для имени параметра неявного значения для методов задания свойств.

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException, IndexOutOfRangeException и AccessViolationException
 ❌ не разрешать явно вызываемые API для явного или неявного вызова <xref:System.NullReferenceException>, <xref:System.AccessViolationException>или <xref:System.IndexOutOfRangeException>. Эти исключения зарезервированы и создаются подсистемой выполнения и в большинстве случаев указывают на ошибку.

 Проследите за проверкой аргументов, чтобы избежать возникновения этих исключений. Создание этих исключений предоставляет сведения о реализации метода, которые могут меняться со временем.

## <a name="stackoverflowexception"></a>StackOverflowException
 ❌ не вызывайте <xref:System.StackOverflowException>явным образом. Исключение должно быть явно вызвано только средой CLR.

 ❌ не перехватывайте `StackOverflowException`.

 Практически невозможно написать управляемый код, который остается единообразным при наличии произвольных переходящих стеков стека. Неуправляемые части среды CLR остаются неизменными с помощью зондов для перемещения передатчиков стека в четко определенные места, а не при резервном копировании из произвольных передатчиков стека.

## <a name="outofmemoryexception"></a>OutOfMemoryException
 ❌ не вызывайте <xref:System.OutOfMemoryException>явным образом. Это исключение возникает только в инфраструктуре среды CLR.

## <a name="comexception-sehexception-and-executionengineexception"></a>ComException, SEHException и ExecutionEngineException
 ❌ не создают явно <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>и <xref:System.Runtime.InteropServices.SEHException>. Эти исключения должны вызываться только инфраструктурой CLR.

 *Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*

 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*

## <a name="see-also"></a>См. также:

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)
- [Правила разработки исключений](../../../docs/standard/design-guidelines/exceptions.md)
