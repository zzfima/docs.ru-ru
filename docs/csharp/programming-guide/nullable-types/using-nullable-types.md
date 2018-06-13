---
title: Использование допускающих значение NULL типов (Руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33336925"
---
# <a name="using-nullable-types-c-programming-guide"></a>Использование допускающих значение NULL типов (Руководство по программированию на C#)
Типы, допускающие значение NULL, могут представлять все значения своего основного типа, а также само значение [NULL](../../../csharp/language-reference/keywords/null.md). Типы, допускающие значение null, объявляются одним из следующих двух способов:  
  
 `System.Nullable<T> variable`  
  
 - или -  
  
 `T? variable`  
  
 `T` — это основной тип для типа, допускающего значение NULL. `T` может быть значением любого типа, включая `struct`, но не ссылочным типом.  
  
 В качестве примера того, когда можно использовать тип, допускающий значение null, рассмотрим обычную переменную типа Boolean, которая может иметь два значения: true и false. У этого типа нет значения, обозначающего "не определено". Во многих приложениях, в первую очередь взаимодействующих с базами данных, переменные могут оказаться в неопределенном состоянии. Например, поле в базе данных может содержать значение true или false, но оно также может вообще не содержать никакого значения. Подобным образом для ссылочных типов можно установить значение `null`, чтобы обозначить тот факт, что они не инициализированы.  
  
 Это несоответствие может создавать лишнюю работу по программированию, в частности, приводить к использованию дополнительных переменных для хранения информации о состоянии, применению специальных значений, и т. п. Модификатор, указывающий, что данный тип допускает значения null, позволяет в языке C# создавать переменные значащего типа, позволяющие указывать для них неопределенное значение.  
  
## <a name="examples-of-nullable-types"></a>Примеры типов, допускающих значение NULL  
 Любой значащий тип может использоваться как основной для типа, допускающего значение null. Пример:  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a>Члены типов, допускающих значение NULL  
 Каждый объект типа, допускающего значение null, имеет два открытых свойства, доступных только для чтения:  
  
-   `HasValue`  
  
     `HasValue` имеет тип `bool`. Для него устанавливается значение `true`, если переменная содержит значение, не равное NULL.  
  
-   `Value`  
  
     `Value` имеет тот же тип, что и базовый тип. Если `HasValue` равно `true`, то свойство `Value` содержит полезное значение. Если `HasValue` имеет значение `false`, доступ к свойству `Value` вызовет исключение <xref:System.InvalidOperationException>.  
  
 В этом примере член `HasValue` используется для проверки того, содержит ли переменная какое-либо значение, прежде чем пытаться его показать.  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 Проверку на наличие полезного значения можно также выполнить, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a>Явные преобразования  
 Тип, допускающий значение NULL, может быть приведен к своему основному типу либо явно, путем приведения типа, либо при помощи свойства `Value`. Пример:  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 Если между двумя типами данных определено пользовательское преобразование типов, то это же преобразование можно также использовать с версиями этих типов, допускающими значение null.  
  
## <a name="implicit-conversions"></a>Неявные преобразования  
 Для переменной типа, допускающего значение NULL, можно установить значение NULL с помощью ключевого слова `null`, как показано в следующем примере:  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 Преобразование из обычного типа в тип, допускающий значение null, является неявным.  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a>Операторы  
 Предопределенные унарные и бинарные операции, а также любые операции, определенные программистом, которые существуют для значащих типов, также можно использовать и с типами, допускающими значение null. Эти операции возвращают значение null, если операнды имеют значение null; в противном случае операция использует содержащееся значение для вычисления результата. Пример:  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 Если при сравнении с допускающими значение NULL типами значение одного из таких типов равно NULL, а второй тип содержит другое значение, то результатом сравнения всегда является `false` , за исключением использования оператора `!=` (не равно). Тут важно не полагать, что если какая-то операция сравнения возвращает `false`, то противоположная ей операция обязательно вернет `true`. В следующем примере число 10 не больше, не меньше и не равно null. Только `num1 != num2` даст `true`.  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 Проверка на равенство двух типов, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.  
  
## <a name="the--operator"></a>?? Оператор  
 Оператор `??` определяет значение по умолчанию, которое используется, когда значение типа, допускающего NULL, присваивается значению типа, не допускающего NULL.  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 Эту операцию также можно использовать с несколькими значениями типа, допускающего null. Пример:  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a>Тип bool?  
 Тип `bool?`, допускающий значение NULL, может содержать три разных значения: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) и [null](../../../csharp/language-reference/keywords/null.md). Сведения о приведении bool? к bool см. в разделе [Практическое руководство. Безопасное приведение bool? к bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).  
  
 Тип Boolean, допускающий значение null, подобен типу Boolean в SQL. Чтобы убедиться, что результаты операторов `&` и `|` согласуются с трехзначным типом Boolean в SQL, предусмотрены следующие предопределенные операторы:  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 Результаты этих операций приведены в следующей таблице:  
  
|X|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|False|false|true|  
|true|null|null|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|null|False|null|  
|null|true|null|true|  
|null|False|False|null|  
|null|null|null|null|  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
 [Упаковка-преобразование типов, допускающих значение NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
