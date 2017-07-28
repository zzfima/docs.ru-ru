---
title: "Новые возможности Visual Basic | Документы Майкрософт"
ms.date: 2017-04-27
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- VB.StartPage.WhatsNew
dev_langs:
- VB
helpviewer_keywords:
- new features, Visual Basic
- what's new [Visual Basic]
- Visual Basic, what's new
ms.assetid: d7e97396-7f42-4873-a81c-4ebcc4b6ca02
caps.latest.revision: 145
author: rpetrusha
ms.author: ronpet
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d3f21e32c162133e70a124da125c30afc7303738
ms.openlocfilehash: 18544a0311e24cf427111e364421db6e9fc27326
ms.contentlocale: ru-ru
ms.lasthandoff: 05/15/2017

---
# <a name="whats-new-for-visual-basic"></a>Новые возможности Visual Basic

В этой статье перечислены названия основных возможностей в каждой версии Visual Basic с подробными описаниями новых и усовершенствованных возможностей в последней версии этого языка программирования.
  
## <a name="current-version"></a>Текущая версия

Visual Basic/Visual Studio .NET 2017   
Описание новых функций см. в статье [Visual Basic 2017](#visual-basic-2017)

## <a name="previous-versions"></a>Предыдущие версии

Visual Basic/Visual Studio .NET 2015   
Описание новых функций см. в статье [Visual Basic 14](#visual-basic-14)

Visual Basic/Visual Studio .NET 2013  
CTP-версии платформы компиляции .NET (Roslyn)

Visual Basic/Visual Studio .NET 2012   
Ключевые слова `Async` и `await`, итераторы, атрибуты сведений о вызывающем объекте

Visual Basic/Visual Studio .NET 2010   
Автоматически реализуемые свойства, инициализаторы коллекций, неявное продолжение строки, динамические типы, универсальная ковариантность и контрвариантность, доступ к глобальному пространству имен

Visual Basic/Visual Studio .NET 2008   
Интегрированные запросы языка (LINQ), XML-литералы, определение локального типа, инициализаторы объектов, анонимные типы, методы расширений, определение локального типа `var`, лямбда-выражения, оператор `if`, типы значений, допускающие значение NULL  

Visual Basic/Visual Studio .NET 2005   
Тип `My` и вспомогательные типы (доступ к приложению, компьютеру, файловой системе, сети)

Visual Basic/Visual Studio .NET 2003   
Операторы поразрядного сдвига, объявление переменных цикла

Visual Basic/Visual Studio .NET 2002   
Первый выпуск Visual Basic .NET

## <a name="visual-basic-2017"></a>Visual Basic 2017

[Кортежи](../programming-guide/language-features/data-types/tuples.md)

Кортежи представляют собой облегченную структуру данных, которая обычно используется для получения сразу нескольких значений за один вызов метода. Как правило, для получения нескольких значений с помощью одного метода необходимо выполнить одно из следующих действий:

- Определить пользовательский тип (`Class` или `Structure`). Это трудоемкое решение.

- Определить один или несколько параметров `ByRef` помимо возврата значения из метода.
 
Поддержка кортежей в Visual Basic позволяет быстро определить кортеж, при необходимости назначить его значениям семантические имена и быстро извлечь его значения. В следующем примере показан вызов метода <xref:System.Int32.TryParse%2A> и получение кортежа.

[!code-vb[Tuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

После этого можно вызвать метод и обработать возвращенный кортеж в коде следующего вида.

[!code-vb[ReturnTuple](../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)] 

**Двоичные литералы и разделители разрядов**

Двоичный литерал можно определить с помощью префикса `&B` или `&b`. Для повышения удобочитаемости в качестве разделителя разрядов можно использовать символ подчеркивания (`_`). В следующем примере обе эти функции используют для того, чтобы назначить значение `Byte` и отобразить его как десятичное, шестнадцатеричное или двоичное число.

[!code-vb[Binary](../../../samples/snippets/visualbasic/getting-started/bin-example.vb#1)]

Дополнительные сведения см. в разделе "Назначения литералов" статей, посвященных типам данных [Byte](../language-reference/data-types/byte-data-type.md#literal-assignments), [Integer](../language-reference/data-types/integer-data-type.md#literal-assignments), [Long](../language-reference/data-types/long-data-type.md#literal-assignments), [Short](../language-reference/data-types/short-data-type.md#literal-assignments), [SByte](../language-reference/data-types/sbyte-data-type.md#literal-assignments), [UInteger](../language-reference/data-types/uinteger-data-type.md#literal-assignments), [ULong](../language-reference/data-types/ulong-data-type.md#literal-assignments) и [UShort](../language-reference/data-types/ushort-data-type.md#literal-assignments).

**Поддержка значений C#, возвращаемых по ссылке**

Начиная с версии 7, C# поддерживает значения, возвращаемые по ссылке. Это значит, что в случае, если вызывающий метод получает значение, возвращаемое по ссылке, он может изменить значение ссылки. Visual Basic не позволяет создавать методы со значениями, возвращаемыми по ссылке, но разрешает получать и изменять такие значения.

Например, следующий класс `Sentence`, написанный на языке C#, включает метод `FindNext`, который выполняет поиск следующего слова в предложении, которое начинается с заданной подстроки. Строка возвращается как значение, возвращаемое по ссылке, а переменная `Boolean`, переданная в метод по ссылке, показывает, дал ли поиск какие-то результаты. Это означает, что вызывающий объект может не только читать, но и изменять возвращаемое значение, а внесенные изменения отражаются в классе `Sentence`.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Проще всего изменить найденное в предложении слово с помощью представленного ниже кода. Обратите внимание на то, что при этом значение назначается не методу, а выражению, которое возвращается этим методом и представляет собой значение, возвращаемое по ссылке.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#1)]

Проблема этого кода состоит в том, что в случае, если совпадений нет, метод возвращает первое слово. Поскольку код в этом примере не проверяет значение аргумента `Boolean`, чтобы определить наличие совпадений, в случае, если совпадений нет, он изменяет первое слово. В следующем примере эта проблема решена — если совпадений нет, первое слово заменяется само на себя.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return.vb#2)]

Лучше использовать вспомогательный метод, в который значение, возвращаемое по ссылке, передается по ссылке. Впоследствии вспомогательный метод сможет изменить аргумент, передаваемый ему по ссылке. Эту задачу решает следующий код.

[!code-vb[Ref-Return](../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

Дополнительные сведения см. в разделе [Значения, возвращаемые по ссылке](../programming-guide/language-features/procedures/ref-return-values.md).

## <a name="visual-basic-14"></a>Visual Basic 14

[Nameof](../../csharp/language-reference/keywords/nameof.md)  
 Можно получить неполное имя строки типа или элемента для использования в сообщении об ошибке, не выполняя жесткого программирования строки.  Это позволяет сохранить правильный код при рефакторинге.  Эта возможность также полезна для прикрепления связей MVC контроллера model-view-controller и инициирования событий изменения свойств.  
  
[Интерполяция строк](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Для создания строк можно использовать выражения интерполяции строк.  Интерполированное строковое выражение выглядит как шаблонная строка, которая содержит выражения.  Интерполированную строку проще понять с точки зрения аргументов, чем [составное форматирование](../../standard/base-types/composite-format.md).  
  
[Доступ к членам и индексация с проверкой на значение NULL](../../csharp/language-reference/operators/null-conditional-operators.md)  
Прежде чем осуществлять доступ к элементу (`?.`) или выполнять операцию с индексом (`?[]`), можно протестировать значение null в очень простой синтаксической конструкции.  Эти операторы позволяют писать меньше кода для проверок значений null, особенно если речь идет о внедрении в структуры данных.  Если левый операнд или объектная ссылка имеет значение null, операция также возвращает значение null.  
  
[Многострочные строковые литералы](../../visual-basic/programming-guide/language-features/strings/string-basics.md)  
 Строковые литералы могут содержать последовательности новых строк.  Прежний обходной путь, связанный с использованием `<xml><![CDATA[...text with newlines...]]></xml>.Value`, больше не потребуется.  
  
Комментарии  
Комментарии можно поместить после неявных продолжений строк, внутри выражений инициализатора и среди условий выражения LINQ.  
  
 Оптимизированное разрешение полных доменных имен  
 Имея код, например `Threading.Thread.Sleep(1000)`, Visual Basic выполняла поиск пространства имен «Потоки», обнаруживала, что это пространство имен было неоднозначным в потоках System.Threading и System.Windows.Threading, и сообщала об ошибке.  Теперь Visual Basic рассматривает оба возможных пространства имен одновременно.  При отображении списка завершения редактор Visual Studio отображает в нем элементы обоих типов.  
  
 Литералы даты первого года  
 Литералы даты могут быть указаны в формате гггг-мм-дд, `#2015-03-17 16:10 PM#`.  
  
 Свойства интерфейса Readonly  
 С помощью свойства readwrite можно реализовать свойства интерфейса readonly.  Интерфейс гарантирует минимальную функциональность и не препятствует функционированию реализующего класса, который разрешает задавать значения для свойства.  
  
 [TypeOf \<выражение> IsNot \<тип>](../../visual-basic/language-reference/operators/typeof-operator.md)  
 Для удобства чтения кода `TypeOf` теперь можно использовать с `IsNot`.  
  
 [#Disable Warning \<ИД> и #Enable Warning \<ИД>](../../visual-basic/language-reference/directives/directives.md)  
 Можно отключить и включить конкретные предупреждения для областей в исходном файле.  
  
 Усовершенствования комментариев в документации XML  
 При написании комментариев к документу разработчик получает доступ к интеллектуальному редактору и поддержку при сборке, что позволяет проверять названия параметров, грамотно обрабатывать `crefs` (универсальные типы, операторы и т. д.), выделение цветом и рефакторинг.  
  
 [Определения частичных модулей и интерфейсов](../../visual-basic/language-reference/modifiers/partial.md)  
 Помимо классов и структур можно также объявлять частичные модули и интерфейсы.  
  
 [Директивы #Region внутри основной части метода](../../visual-basic/language-reference/directives/region-directive.md)  
 Разделители #Region... #End Region можно поместить в любом месте файла, внутри функций и даже в основной части функции.  
  
 [Определения переопределений являются неявными перегрузками](../../visual-basic/language-reference/modifiers/overrides.md)  
 Если добавить в определение модификатор `Overrides`, компилятор неявно добавляет `Overloads`, чтобы в общих случаях можно было вводить меньше кода.  
  
 В аргументах атрибутов можно использовать объекты CObj.  
 Компилятор, используемый для вывода ошибки, связанной с тем, что при использовании в конструкциях атрибутов CObj(...) не являлся константой.  
  
 Объявление и использование неоднозначных методов из разных интерфейсов  
 Ранее следующий код выдавал ошибки, которые не позволяли объявить `IMock` или вызвать `GetDetails` (если эти значения были объявлены в C#).  
  
```vb  
Interface ICustomer  
  Sub GetDetails(x As Integer)  
End Interface  
  
Interface ITime  
  Sub GetDetails(x As String)  
End Interface  
  
Interface IMock : Inherits ICustomer, ITime  
  Overloads Sub GetDetails(x As Char)  
End Interface  
  
Interface IMock2 : Inherits ICustomer, ITime  
End Interface  
```  
  
 Теперь компилятор использует стандартные правила разрешения перегрузки, чтобы выбрать оптимальную `GetDetails` для вызова, а в Visual Basic можно объявить связи интерфейса, как показано в примере.  
  
## <a name="see-also"></a>См. также  
 [Новые возможности Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/ide/whats-new-in-visual-studio)

