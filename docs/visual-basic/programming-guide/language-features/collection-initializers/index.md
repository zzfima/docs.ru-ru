---
title: Инициализаторы коллекций
ms.date: 07/20/2015
f1_keywords:
- vb.CollectionInitializer
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: a9290329-77b0-4fdf-ae75-8fc17287f469
ms.openlocfilehash: fbdd116298c530ae54677631eff7dac2f22c0fe2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346784"
---
# <a name="collection-initializers-visual-basic"></a>Инициализаторы коллекций (Visual Basic)

*Инициализаторы набора* предлагают сокращенный синтаксис для создания коллекций и заполнения их начальным набором значений. Инициализаторы набора полезны при создании коллекции из набора известных значений и ее последующей проверки. Это может быть список команд меню или категорий, исходный набор числовых значений, статический список строк, например названий дней или месяцев либо географических расположений (список штатов), и многое другое.

Более подробную информацию о коллекциях см. в статье [Коллекции](../../../../visual-basic/programming-guide/concepts/collections.md).

Инициализатор набора определяется по ключевому слову `From`, за которым следуют фигурные скобки (`{}`). Это похоже на синтаксис литерала массива, описанный в разделе [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md). Следующие примеры демонстрируют различные способы применения инициализаторов для создания коллекций.

[!code-vb[VbVbalrCollectionInitializers#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#1)]

> [!NOTE]
> Инициализаторы набора также доступны в C#. Инициализаторы набора в C# предлагают те же функциональные возможности, что и в Visual Basic. Подробнее об инициализаторах набора C# см. в разделе [Инициализаторы объекта и набора](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).

## <a name="syntax"></a>Синтаксис

Инициализатор набора состоит из списка разделенных запятыми и заключенных в фигурные скобки (`{}`) значений, которым предшествует ключевое слово `From`, как показано в следующем примере кода.

[!code-vb[VbVbalrCollectionInitializers#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#2)]

При создании коллекции, например <xref:System.Collections.Generic.List%601> или <xref:System.Collections.Generic.Dictionary%602>, перед инициализатором набора необходимо указать тип коллекции, как показано в следующем примере кода.

[!code-vb[VbVbalrCollectionInitializers#13](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#13)]

> [!NOTE]
> Не допускается одновременно использовать инициализатор и набора и объекта для инициализации одного и того же объекта коллекции. Инициализаторы объекта можно использовать для инициализации объектов в инициализаторе набора.

## <a name="creating-a-collection-by-using-a-collection-initializer"></a>Creating a Collection by Using a Collection Initializer

При создании коллекции с помощью инициализатора набора каждое указываемое в инициализаторе значение передается в соответствующий метод `Add` коллекции. Например, при создании <xref:System.Collections.Generic.List%601> с помощью инициализатора набора строковое значение в инициализаторе передается методу <xref:System.Collections.Generic.List%601.Add%2A>. Если вы хотите создать коллекцию с помощью инициализатора набора, следует указать допустимый тип коллекции. Примеры допустимых типов коллекций — классы, которые реализуют интерфейс <xref:System.Collections.Generic.IEnumerable%601> или наследуют от класса <xref:System.Collections.CollectionBase>. Указанный тип должен также предоставлять метод `Add`, отвечающий следующим условиям.

- Метод `Add` должен быть доступен из области, в которой вызывается инициализатор набора. Если инициализатор набора применяется в сценарии, в котором допускается обращение к методам коллекции, не являющимся открытыми, метод `Add` не должен обязательно быть открытым.

- Метод `Add` должен быть членом экземпляра или членом `Shared` класса коллекции либо методом расширения.

- Должен существовать метод `Add`, который может сопоставляться на основе правил разрешения перегрузки с типами, предоставляемыми в инициализаторе набора.

 В следующем примере кода показано, как создать с помощью инициализатора набора коллекцию `List(Of Customer)`. При выполнении кода каждый объект `Customer` передается методу `Add(Customer)` универсального списка.

[!code-vb[VbVbalrCollectionInitializers#9](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#9)]

В следующем примере кода показан эквивалентный код, в котором инициализатор набора не используется.

[!code-vb[VbVbalrCollectionInitializers#10](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#10)]

Если метод `Add` коллекции имеет параметры, сопоставимые с конструктором объекта `Customer`, значения параметров для метода `Add` можно вложить в инициализаторы набора, как описывается в следующем разделе. Если у коллекции такого метода `Add` нет, его можно создать как метод расширения. Пример создания метода `Add` как метода расширения для коллекции см. в разделе [Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md). Пример создания настраиваемой коллекции, которую можно использовать с инициализатором набора, см. в разделе [Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md).

## <a name="nesting-collection-initializers"></a>Инициализаторы набора с вложениями

В инициализатор набора можно вкладывать значения, чтобы указать конкретную перегрузку метода `Add` для создаваемой коллекции. Значения, передаваемые методу `Add`, должны быть разделены запятыми и заключены в фигурные скобки (`{}`) так же, как в литерале массива или инициализаторе набора.

При создании коллекции с помощью вложенных значений каждый элемент списка вложенных значений передается в качестве аргумента методу `Add`, который соответствует типам элементов. В следующем примере кода создается коллекция <xref:System.Collections.Generic.Dictionary%602>, в которой ключи относятся к типу `Integer`, а значения — к типу `String`. Каждый из списков вложенных значений сопоставляется с методом <xref:System.Collections.Generic.Dictionary%602.Add%2A> для `Dictionary`.

[!code-vb[VbVbalrCollectionInitializers#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#5)]

Предыдущий пример кода эквивалентен следующему коду.

[!code-vb[VbVbalrCollectionInitializers#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializers/VB/Module1.vb#6)]

Методу `Add` типа коллекции передаются только списки вложенных значений первого уровня вложения. Более глубокие уровни вложения обрабатываются как литералы массива, а списки вложенных значений не сопоставляются с методом `Add` ни в одной из коллекций.

## <a name="related-topics"></a>См. также

|Заголовок|Описание|
|---|---|
|[Практическое руководство. Создание метода расширения Add, используемого инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)|Описывает создание метода расширения `Add`, который можно использовать для заполнения коллекции значениями из инициализатора набора.|
|[Практическое руководство. Создание коллекции, используемой инициализатором набора](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)|Описывает, как активировать использование инициализатора набора, включив метод `Add` в класс коллекции, реализующий `IEnumerable`.|

## <a name="see-also"></a>См. также

- [Коллекции](../../../../visual-basic/programming-guide/concepts/collections.md)
- [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)
- [Автоматически реализуемые свойства](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [How to: Initialize an Array Variable in Visual Basic](../../../../visual-basic/programming-guide/language-features/arrays/how-to-initialize-an-array-variable.md) (Практическое руководство. Инициализация переменной массива в Visual Basic)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Практическое руководство. Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
