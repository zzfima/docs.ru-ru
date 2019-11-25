---
title: Основные принципы и терминология (функциональное преобразование)
ms.date: 07/20/2015
ms.assetid: 24fd244d-ebae-4721-8858-89bb544aea0b
ms.openlocfilehash: efc1fc5bb738e3d5d9d3fa2a8226c37da69c045c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345699"
---
# <a name="concepts-and-terminology-functional-transformation-visual-basic"></a>Concepts and Terminology (Functional Transformation) (Visual Basic)
В данном разделе вводятся основные понятия и терминология чисто функциональных преобразований. Подход с использованием функциональных преобразований для преобразования данных порождает код, который обычно быстрее для программирования, более выразительный и легче для отладки и сопровождения, чем порожденный с использованием традиционного императивного программирования.

Заметим, что темы в данном разделе не претендуют на подробное объяснение функционального программирования. Но при этом они определяют некоторые возможности функционального программирования, которые позволяют легче переводить XML из одной формы в другую.

## <a name="what-is-pure-functional-transformation"></a>Что такое чисто функциональное преобразование?

При *чисто функциональном преобразовании* набор функций, называемых *чистыми функциями*, определяет способ преобразования набора структурированных данных из одной формы в другую. Слово "чистые" указывает на то, что функции *допускают композицию*, то есть отвечают следующим требованиям:

- *Замкнутые*, то есть они должны свободно упорядочиваться и переупорядочиваться без вовлечения остальных частей программы и взаимных зависимостей от них. Чистые преобразования не имеют представления о своей среде и не влияют на нее. Иными словами, использованные при преобразовании функции не имеют *побочных эффектов*.

- *Без учета состояния*, то есть исполнение одной и той же функции или определенного набора функций с одинаковыми входными данными будет всегда приводить к одинаковым выходным данным. Чистые преобразования не знают о предыдущих использованиях.

> [!IMPORTANT]
> До конца данного учебника термин «чистая возможность» используется в основном для указания подхода к программированию, а не специальной характеристики языка.
>
> Note that pure functions must be implemented as functions in Visual Basic.
>
> Также не надо путать чистые функции с чисто виртуальными методами в C++. Второй случай показывает, что содержащийся класс абстрактный и текст метода не указан.

### <a name="functional-programming"></a>Функциональное программирование

Термин *функциональное программирование* обозначает такой подход к программированию, при котором непосредственно поддерживаются чисто функциональные преобразования.

Исторически языки функционального программирования общего назначения, такие как ML, Scheme, Haskell и F#, представляли интерес в первую очередь для научного сообщества. Although it has always been possible to write pure functional transformations in Visual Basic, the difficulty of doing so has not made it an attractive option to most programmers. With later versions of Visual Basic, however, new language constructs such as lambda expressions and type inference make it functional programming much easier and more productive.

For more information about functional programming, see [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md).

#### <a name="domain-specific-fp-languages"></a>Предметные языки функционального программирования

Не смотря на то что основные языки функционального программирования широко не используются, специальные предметные языки функционального программирования имеют больший успех. Например, каскадные таблицы стилей (CSS) используются для определения вида многих веб-страниц, а преобразования XSLT широко используются в обработке XML-данных. Дополнительные сведения об XSLT см. в разделе [Преобразования XSLT](../../../../standard/data/xml/xslt-transformations.md).

## <a name="terminology"></a>Терминология

Следующие таблицы определяют некоторые термины, связанные с функциональными преобразованиями.

функция высокого порядка (первого класса) \
Функция, которая может быть интерпретирована как программный объект. Например, функция высокого порядка может быть передана и возвращена другими функциями. In Visual Basic, delegates and lambda expressions are language features that support higher-order functions. Для написания функции высокого порядка необходимо объявить один или несколько аргументов для принятия делегатов, при этом обычно используются лямбда-выражения. Многие стандартные операторы запроса являются функциями высокого порядка.

For more information, see [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

лямбда-выражение \
По сути это встроенная анонимная функция, которая может использоваться, когда тип делегата неизвестен. Это упрощенное значение лямбда-выражений, однако оно достаточно для целей данного учебника.

Дополнительные сведения см. в разделе [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).

коллекция \
Структурированный набор данных обычно стандартного типа. Для обеспечения совместимости с LINQ коллекция должна реализовывать интерфейс <xref:System.Collections.IEnumerable> или интерфейс <xref:System.Linq.IQueryable> (или один из их основных прототипов <xref:System.Collections.Generic.IEnumerator%601> или <xref:System.Linq.IQueryable%601>).

кортеж (анонимные типы) \
Как математическое понятие, кортеж представляет собой конечную последовательность объектов, каждый определенного типа. Кортеж называется также упорядоченным списком. Анонимные типы представляют собой языковую реализацию этой концепции, которая позволяет объявить класс неименованного типа и одновременно создать экземпляр объекта этого типа.

For more information, see  [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

определение типов (скрытое типизирование) \
Возможность компилятора определить тип переменной при отсутствии явной декларации типа.

For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).

отложенное исполнение и отложенные вычисления \
Задержка вычисления выражения до тех пор, пока его результат не станет нужен. В коллекциях поддерживается отложенное исполнение.

For more information, see [Basic Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md) and [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

Эти языковые возможности будут использованы в образцах кода на протяжении данного раздела.

## <a name="see-also"></a>См. также

- [Introduction to Pure Functional Transformations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [Functional Programming vs. Imperative Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
