---
title: "Практическое руководство. Сравнение строк (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], comparison
- comparing strings [C#]
ms.assetid: e1268e28-ee98-4695-98e9-92280f1c33c0
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4837fa57c962cba841ffcc83c5bd4475a4faff0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-compare-strings-c-programming-guide"></a>Практическое руководство. Сравнение строк (Руководство по программированию в C#)

В результате сравнения строк выясняется, что одна строка больше или меньше другой или что обе строки одинаковы. Правила, используемые для определения результата, отличаются в зависимости от выполнения *порядкового сравнения* или *сравнения с учетом языка и региональных параметров*. Для каждой отдельной задачи важно использовать соответствующий вид сравнения.

 Чтобы сравнить или отсортировать значения двух строк независимо от лингвистических соглашений, используйте базовые порядковые сравнения. В базовом порядковом сравнении (`System.StringComparison.Ordinal`) учитывается регистр, что означает необходимость соответствия символов двух строк: "and" — не то же, что "And" или "AND". Часто используется вариация `System.StringComparison.OrdinalIgnoreCase`, которая соответствует написаниям and, And и AND. `StringComparison.OrdinalIgnoreCase` часто используется для сравнения имен файлов, имен путей, сетевых путей и любой другой строки, значение которой не меняется в зависимости от языка системы компьютера пользователя. Для получения дополнительной информации см. <xref:System.StringComparison?displayProperty=nameWithType>.

 Сравнения с учетом языка и региональных параметров обычно используются для сравнения и сортировки строк, введенных конечными пользователями, поскольку символы и правила сортировки этих строк могут различаться в зависимости от языкового стандарта компьютера пользователя. Даже строки, содержащие идентичные символы, могут быть отсортированы по-разному, в зависимости от языка и региональных параметров текущего потока.

> [!NOTE]
> При сравнении строк следует использовать методы, которые явно указывают, какой вид сравнения следует выполнить. Это делает код намного более понятным и удобочитаемым. По возможности используйте перегрузки методов классов <xref:System.String?displayProperty=nameWithType> и <xref:System.Array?displayProperty=nameWithType>, которые принимают параметр перечисления <xref:System.StringComparison> — это позволит вам указать тип выполняемого сравнения. По возможности рекомендуется избегать использования операторов `==` и `!=` при сравнении строк. Также старайтесь не использовать методы экземпляров <xref:System.String.CompareTo%2A?displayProperty=nameWithType>, поскольку ни одна из перегрузок не принимает <xref:System.StringComparison>.

## <a name="example"></a>Пример

В следующем примере показано, как правильно сравнивать строки, значения которых не изменятся на основе языкового стандарта компьютера пользователя. Кроме того, здесь демонстрируется свойство *интернирования строк* C#. При объявлении программой двух или более идентичных переменных строк компилятор сохраняет их в одном расположении. Вызвав метод <xref:System.Object.ReferenceEquals%2A>, можно увидеть, что две строки фактически ссылаются на один и тот же объект в памяти. Чтобы избежать интернирования, используйте метод <xref:System.String.Copy%2A?displayProperty=nameWithType>, как показано в примере.

[!code-csharp[csProgGuideStrings#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#11)]

## <a name="example"></a>Пример

В следующем примере показано, как применять предпочтительный метод сравнения строк, используя методы <xref:System.String?displayProperty=nameWithType>, принимающие перечисление <xref:System.StringComparison>. Обратите внимание на то, что методы экземпляров <xref:System.String.CompareTo%2A?displayProperty=nameWithType> здесь не используются, поскольку ни одна из перегрузок не принимает <xref:System.StringComparison>.

[!code-csharp[csProgGuideStrings#31](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#31)]

## <a name="example"></a>Пример

В следующем примере показано, как сортировать и искать строки в массиве с учетом языка и региональных параметров с помощью статических методов <xref:System.Array>, принимающих параметр <xref:System.StringComparer?displayProperty=nameWithType>.

[!code-csharp[csProgGuideStrings#32](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#32)]

Классы коллекций, такие как <xref:System.Collections.Hashtable?displayProperty=nameWithType>, <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>, и <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, имеют конструкторы, принимающие параметр <xref:System.StringComparer?displayProperty=nameWithType>, если типом элементов или ключей является `string`. В целом, по возможности следует использовать эти конструкторы и задавать либо `Ordinal`, либо `OrdinalIgnoreCase`.

## <a name="see-also"></a>См. также
 <xref:System.Globalization.CultureInfo?displayProperty=nameWithType>  
 <xref:System.StringComparer?displayProperty=nameWithType>  
 [Строки](../../../csharp/programming-guide/strings/index.md)  
 [Сравнение строк в .NET Framework](../../../standard/base-types/comparing.md)  
 [Глобализация и локализация приложений](/visualstudio/ide/globalizing-and-localizing-applications)