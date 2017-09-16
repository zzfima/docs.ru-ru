---
title: "Практическое руководство. Сравнение строк (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 70bd8f52971115a36626961c2c605f2f93c1ae6b
ms.openlocfilehash: ed376960e0b3bb793b377cc8fac2fdefa030dcc0
ms.contentlocale: ru-ru
ms.lasthandoff: 09/09/2017

---
# <a name="how-to-compare-strings-c-programming-guide"></a>Практическое руководство. Сравнение строк (Руководство по программированию в C#)

В результате сравнения строк выясняется, что одна строка больше или меньше другой или что обе строки одинаковы. Правила, используемые для определения результата, отличаются в зависимости от выполнения *порядкового сравнения* или *сравнения с учетом языка и региональных параметров*. Для каждой отдельной задачи важно использовать соответствующий вид сравнения.

 Чтобы сравнить или отсортировать значения двух строк независимо от лингвистических соглашений, используйте базовые порядковые сравнения. В базовом порядковом сравнении (`System.StringComparison.Ordinal`) учитывается регистр, что означает необходимость соответствия символов двух строк: "and" — не то же, что "And" или "AND". Часто используется вариация `System.StringComparison.OrdinalIgnoreCase`, которая соответствует написаниям and, And и AND. `StringComparison.OrdinalIgnoreCase` часто используется для сравнения имен файлов, имен путей, сетевых путей и любой другой строки, значение которой не меняется в зависимости от языка системы компьютера пользователя. Для получения дополнительной информации см. <xref:System.StringComparison?displayProperty=fullName>.

 Сравнения с учетом языка и региональных параметров обычно используются для сравнения и сортировки строк, введенных конечными пользователями, поскольку символы и правила сортировки этих строк могут различаться в зависимости от языкового стандарта компьютера пользователя. Даже строки, содержащие идентичные символы, могут быть отсортированы по-разному, в зависимости от языка и региональных параметров текущего потока.

> [!NOTE]
> При сравнении строк следует использовать методы, которые явно указывают, какой вид сравнения следует выполнить. Это делает код намного более понятным и удобочитаемым. По возможности используйте перегрузки методов классов <xref:System.String?displayProperty=fullName> и <xref:System.Array?displayProperty=fullName>, которые принимают параметр перечисления <xref:System.StringComparison> — это позволит вам указать тип выполняемого сравнения. По возможности рекомендуется избегать использования операторов `==` и `!=` при сравнении строк. Также старайтесь не использовать методы экземпляров <xref:System.String.CompareTo%2A?displayProperty=fullName>, поскольку ни одна из перегрузок не принимает <xref:System.StringComparison>.

## <a name="example"></a>Пример

В следующем примере показано, как правильно сравнивать строки, значения которых не изменятся на основе языкового стандарта компьютера пользователя. Кроме того, здесь демонстрируется свойство *интернирования строк* C#. При объявлении программой двух или более идентичных переменных строк компилятор сохраняет их в одном расположении. Вызвав метод <xref:System.Object.ReferenceEquals%2A>, можно увидеть, что две строки фактически ссылаются на один и тот же объект в памяти. Чтобы избежать интернирования, используйте метод <xref:System.String.Copy%2A?displayProperty=fullName>, как показано в примере.

[!code-csharp[csProgGuideStrings#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#11)]

## <a name="example"></a>Пример

В следующем примере показано, как применять предпочтительный метод сравнения строк, используя методы <xref:System.String?displayProperty=fullName>, принимающие перечисление <xref:System.StringComparison>. Обратите внимание на то, что методы экземпляров <xref:System.String.CompareTo%2A?displayProperty=fullName> здесь не используются, поскольку ни одна из перегрузок не принимает <xref:System.StringComparison>.

[!code-csharp[csProgGuideStrings#31](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#31)]

## <a name="example"></a>Пример

В следующем примере показано, как сортировать и искать строки в массиве с учетом языка и региональных параметров с помощью статических методов <xref:System.Array>, принимающих параметр <xref:System.StringComparer?displayProperty=fullName>.

[!code-csharp[csProgGuideStrings#32](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#32)]

Классы коллекций, такие как <xref:System.Collections.Hashtable?displayProperty=fullName>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>, и <xref:System.Collections.Generic.List%601?displayProperty=fullName>, имеют конструкторы, принимающие параметр <xref:System.StringComparer?displayProperty=fullName>, если типом элементов или ключей является `string`. В целом, по возможности следует использовать эти конструкторы и задавать либо `Ordinal`, либо `OrdinalIgnoreCase`.

## <a name="see-also"></a>См. также
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.StringComparer?displayProperty=fullName>   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [Сравнение строк](../../../standard/base-types/comparing.md)   
 [Глобализация и локализация приложений](/visualstudio/ide/globalizing-and-localizing-applications)
