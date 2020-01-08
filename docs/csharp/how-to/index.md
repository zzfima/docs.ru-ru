---
title: Статьи с практическими руководствами (руководств по языку C#)
description: Коллекция советов и кратких конкретных примеров кода
ms.date: 12/20/2017
ms.openlocfilehash: e6cb657726b82a1710bbcd596fe48037b5c26352
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75339219"
---
# <a name="how-to-c"></a>Практическое руководство (C#)

В практическом руководстве по языку C# в разделе с инструкциями содержатся ответы на часто задаваемые вопросы. В некоторых случаях статьи могут быть указаны в нескольких разделах. Мы хотели упростить их обнаружение при использовании нескольких вариантов поиска.

## <a name="general-c-concepts"></a>Основные понятия C#

Существует несколько общих советов и рекомендаций для разработчиков на C#:

- [Инициализация объектов с помощью инициализатора объектов](../programming-guide/classes-and-structs/how-to-initialize-objects-by-using-an-object-initializer.md).
- [Различия между передачей структуры и класса в метод](../programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md).
- [Использование перегрузки операторов](../language-reference/operators/operator-overloading.md).
- [Реализация и вызов пользовательского метода расширения](../programming-guide/classes-and-structs/how-to-implement-and-call-a-custom-extension-method.md).
- Даже программистам на C# может потребоваться [использовать пространство имен `My` из Visual Basic](../programming-guide/namespaces/how-to-use-the-my-namespace.md).
- [Создание метода для типа `enum` с помощью методов расширения](../programming-guide/classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

### <a name="class-and-struct-members"></a>Члены класса и структуры

Классы и структуры создаются для реализации программы. При написании классов или структур часто используются перечисленные ниже методы.

- [Объявление автоматически реализуемых свойств](../programming-guide/classes-and-structs/how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).
- [Объявление и использование свойств чтения и записи](../programming-guide/classes-and-structs/how-to-declare-and-use-read-write-properties.md).
- [Определение констант](../programming-guide/classes-and-structs/how-to-define-constants.md).
- [Переопределение метода `ToString` для предоставления строковых выходных данных](../programming-guide/classes-and-structs/how-to-override-the-tostring-method.md).
- [Определение абстрактных свойств](../programming-guide/classes-and-structs/how-to-define-abstract-properties.md).
- [Использование возможностей XML-документации для документирования кода](../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).
- [Явная реализация членов интерфейса](../programming-guide/interfaces/how-to-explicitly-implement-interface-members.md) для обеспечения краткости открытого интерфейса.
- [Явная реализация членов двух интерфейсов](../programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md).

### <a name="working-with-collections"></a>Работа с коллекциями

Следующие статьи содержат сведения о работе с коллекциями данных.

- [Инициализация словаря с помощью инициализатора коллекций](../programming-guide/classes-and-structs/how-to-initialize-a-dictionary-with-a-collection-initializer.md).

## <a name="working-with-strings"></a>Работа со строками

Строки являются основным типом данных, используемым для отображения текста или работы с ним. В этих статьях приводятся распространенные варианты использования строк.

- [Сравнение строк](compare-strings.md).
- [Изменение содержимого строки](modify-string-contents.md).
- [Определение того, представляет ли строка число](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Использование `String.Split` для разделения строк](parse-strings-using-split.md).
- [Объединение нескольких строк в одну](concatenate-multiple-strings.md).
- [Поиск текста в строке](search-strings.md).

## <a name="convert-between-types"></a>Преобразование типов

Может потребоваться преобразовать объект к другому типу.

- [Определение того, представляет ли строка число](../programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md).
- [Преобразование строк, представляющих шестнадцатеричные значения, и числа](../programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).
- [Преобразование строки в `DateTime`](../../standard/base-types/parsing-datetime.md).
- [Преобразование массива байтов в значение типа int](../programming-guide/types/how-to-convert-a-byte-array-to-an-int.md).
- [Преобразование строки в число](../programming-guide/types/how-to-convert-a-string-to-a-number.md).
- [Использование операторов сопоставления шаблонов `as` и `is` для безопасного приведения к другому типу](../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).
- [Определение пользовательского преобразования типов.](../language-reference/operators/user-defined-conversion-operators.md)
- [Определение того, допускает ли тип значения NULL](../language-reference/builtin-types/nullable-value-types.md#how-to-identify-a-nullable-value-type).
- [Преобразование между типами значений, допускающие значения NULL, и типами, не допускающими значения NULL](../language-reference/builtin-types/nullable-value-types.md#conversion-from-a-nullable-value-type-to-an-underlying-type).

## <a name="equality-and-ordering-comparisons"></a>Упорядочение и сравнение на равенство

Можно создать типы, которые определяют собственные правила проверки на равенство или определяют естественное упорядочение объектов этого типа.

- [Проверка на равенство на основе ссылок](../programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).
- [Определение равенства на основе значений для типа](../programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).

## <a name="exception-handling"></a>Обработка исключений

В программах на .NET сообщения о неудачных завершениях методов выводятся путем создания исключений. В следующих статьях вы узнаете, как работать с исключениями.

- [Обработка исключений с помощью `try` и `catch`](../programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md).
- [Очистка ресурсов с помощью предложений `finally`](../programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md).
- [Восстановление в результате возникновения исключений, несовместимых с CLS](../programming-guide/exceptions/how-to-catch-a-non-cls-exception.md).

## <a name="delegates-and-events"></a>Делегаты и события

Делегаты и события предоставляют возможность формирования стратегий использования слабосвязанных блоков кода.

- [Объявление, создание и использование делегатов](../programming-guide/delegates/how-to-declare-instantiate-and-use-a-delegate.md).
- [Объединение многоадресных делегатов](../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).

События предоставляют механизм публикации уведомлений или подписки на них.

- [Подписка и отмена подписки на события](../programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).
- [Реализация событий, объявленных в интерфейсах](../programming-guide/events/how-to-implement-interface-events.md).
- [Соответствие рекомендациям .NET Framework при публикации событий кодом](../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).
- [Создание событий, определенных в базовых классах, из производных классов](../programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md).
- [Реализация пользовательских методов доступа к событиям](../programming-guide/events/how-to-implement-custom-event-accessors.md).

## <a name="linq-practices"></a>Рекомендации по LINQ

LINQ позволяет создавать код для запросов к любому источнику данных, который поддерживает шаблон выражения запроса LINQ. Сведения в следующих статьях помогут понять принципы использования шаблонов и работы с различными источниками данных.

- [Запрос коллекции](../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).
- [Использование лямбда-выражений в запросах](../programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-in-a-query.md).
- [Использование `var` в выражениях запросов](../programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).
- [Возвращение поднаборов свойств элементов из запроса](../programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).
- [Создание запросов со сложной фильтрацией](../programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md).
- [Сортировка элементов источника данных](../programming-guide/concepts/linq/how-to-sort-elements.md).
- [Сортировка элементов по нескольким ключам](../programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md).
- [Управление типом проекции](../programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md).
- [Подсчет вхождений значения в исходной последовательности](../programming-guide/concepts/linq/how-to-count-occurrences-of-a-word-in-a-string-linq.md).
- [Вычисление промежуточных значений](../programming-guide/concepts/linq/how-to-calculate-intermediate-values.md).
- [Слияние данных из нескольких источников](../programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md).
- [Нахождение разности наборов между двумя последовательностями](../programming-guide/concepts/linq/how-to-find-the-set-difference-between-two-lists-linq.md).
- [Отладка пустых результатов запроса](../programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md).
- [Добавление настраиваемых методов в запросы LINQ](../programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md).

## <a name="multiple-threads-and-async-processing"></a>Несколько потоков и асинхронная обработка

В современных программах часто используются асинхронные операции. Сведения о работе с ними приводятся в следующих статьях.

- [Повышение производительности асинхронных операций с помощью `System.Threading.Tasks.Task.WhenAll`](../programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).
- [Параллельное выполнение нескольких веб-запросов с помощью `async` и `await`](../programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md).
- [Использование пула потоков](../../standard/threading/the-managed-thread-pool.md#using-the-thread-pool).

## <a name="command-line-args-to-your-program"></a>Аргументы командной строки для программы

Как правило, в программах на C# используются аргументы командной строки. В следующих статьях содержатся сведения о доступе к этим аргументам командной строки и их обработке.

- [Получение всех аргументов командной строки с помощью `for`](../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md).
