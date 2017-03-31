---
title: "Новые возможности Visual Basic | Документы Майкрософт"
ms.date: 2015-07-20
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
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 55cf69a06a047c12f027007ed7180bf74307f2c9
ms.lasthandoff: 03/13/2017

---
# <a name="whats-new-for-visual-basic"></a>Новые возможности Visual Basic
На этой странице перечислены названия основных возможностей в каждой версии Visual Basic с описаниями новых и усовершенствованных возможностей в последней версии этого языка программирования.  
  
## <a name="previous-versions"></a>Предыдущие версии  
 Visual Basic/Visual Studio .NET 2002  
 Первый выпуск  
  
 Visual Basic/Visual Studio .NET 2003  
 Операторы поразрядного сдвига, объявление переменных цикла  
  
 Visual Basic/Visual Studio .NET 2005  
 `My` тип и вспомогательные типы (доступ к приложению, компьютеру, файловой системе, сети)  
  
 Visual Basic/Visual Studio .NET 2008  
 Интегрированные запросы языка (LINQ), XML-литералы, определение локального типа, инициализаторы объектов, анонимные типы, методы расширений, определение локального типа `var`, лямбда-выражения, оператор `if`, типы значений, допускающие значение NULL  
  
 Visual Basic/Visual Studio .NET 2010  
 Автоматически реализуемые свойства, инициализаторы коллекций, неявное продолжение строки, динамические типы, универсальная ковариантность и контрвариантность, доступ к глобальному пространству имен  
  
 Visual Basic/Visual Studio .NET 2012  
 `Async` / `await`, итераторы, атрибуты сведений о вызывающем объекте  
  
 Visual Basic/Visual Studio .NET 2013  
 CTP-версии платформы компиляции .NET (Roslyn)  
  
 Visual Basic/Visual Studio .NET 2015  
 Текущая версия, см. ниже  
  
## <a name="current-version"></a>Текущая версия  
 [Nameof](../../csharp/language-reference/keywords/nameof.md)  
 Можно получить неполное имя строки типа или элемента для использования в сообщении об ошибке, не выполняя жесткого программирования строки.  Это позволяет сохранить правильный код при рефакторинге.  Эта возможность также полезна для прикрепления связей MVC контроллера model-view-controller и инициирования событий изменения свойств.  
  
 [Интерполяция строк](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Для создания строк можно использовать выражения интерполяции строк.  Интерполированное строковое выражение выглядит как шаблонная строка, которая содержит выражения.  Интерполированную строку проще понять с точки зрения аргументов, чем [составное форматирование](../../standard/base-types/composite-format.md).  
  
 [Определяемый условием Null доступ к членам и индексация](../../csharp/language-reference/operators/null-conditional-operators.md)  
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
