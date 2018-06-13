---
title: Использование свойств (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- set accessor [C#]
- get accessor [C#]
- properties [C#], about properties
ms.assetid: f7f67b05-0983-4cdb-96af-1855d24c967c
ms.openlocfilehash: f0d470d2c38a07db9a936fc645b7a97aa12a7f84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339752"
---
# <a name="using-properties-c-programming-guide"></a>Использование свойств (Руководство по программированию в C#)
Свойства сочетают в себе возможности полей и методов. Пользователю объекта свойство представляется как поле, и для доступа к нему применяется тот же синтаксис. При реализации класса свойство представляется в виде одного или двух блоков кода для методов доступа [get](../../../csharp/language-reference/keywords/get.md) и (или) [set](../../../csharp/language-reference/keywords/set.md). Блок кода для метода доступа `get` выполняется только при считывании свойства, а для метода `set` — при присвоении свойству нового значения. Свойство без метода доступа `set` доступно только для чтения. Свойство без метода доступа `get` доступно только для записи. Свойство, для которого определены оба этих метода, доступно для чтения и записи.  
  
 В отличие от полей, свойства не классифицируются как переменные. Соответственно, нельзя передать свойство в качестве параметра [ref](../../../csharp/language-reference/keywords/ref.md) или [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md).  
  
 Свойства нашли широкое применение в программировании. Их можно использовать для проверки данных перед подтверждением изменения; для прозрачного предоставления доступа к данным класса, которые фактически извлекаются из других источников, например из базы данных; для выполнения действия при изменении данных (например, в этом случае может создаваться событие или изменяться значение других полей).  
  
 При объявлении свойств в блоке класса указывается уровень доступа поля, затем тип и имя свойства, а после этого блок кода, в котором объявляются методы доступа `get` и (или) `set`. Пример:  
  
 [!code-csharp[csProgGuideProperties#7](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_1.cs)]  
  
 В этом примере `Month` объявляется как свойство, а метод доступа `set` обеспечивает установку значения `Month` в диапазоне от 1 до 12. Для отслеживания фактического значения свойство `Month` использует частное поле. Фактическое местоположение данных свойства часто называется "резервным хранилищем". Как правило, в качестве резервного хранилища свойства используют частные поля. Поле помечается как частное для того, чтобы гарантировать возможность его изменения только посредством вызова свойства. Дополнительные сведения об ограничениях открытого и закрытого доступа см. в разделе [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Автоматически реализуемые свойства поддерживают упрощенный синтаксис для простых объявлений свойств. Дополнительные сведения см. в разделе [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## <a name="the-get-accessor"></a>Метод доступа get  
 Тело метода доступа `get` похоже на тело метода. Оно должно возвращать значение заданного типа свойства. Выполнение метода доступа `get` эквивалентно считыванию значения поля. Например, если включена оптимизация и метод доступа `get` возвращает частную переменную, вызов метода доступа `get` определяется компилятором как встроенный, что позволяет исключить затраты ресурсов на вызов метода. Тем не менее виртуальный метод доступа `get` не может определяться как встроенный, поскольку во время компиляции компилятору не известно, как метод может быть фактически вызван во время выполнения. Ниже показан метод доступа `get`, возвращающий значение частного поля `name`:  
  
 [!code-csharp[csProgGuideProperties#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_2.cs)]  
  
 При ссылке на свойство (кроме случаев, когда свойство является целью присваивания) вызывается метод доступа `get`, который считывает значение свойства. Пример:  
  
 [!code-csharp[csProgGuideProperties#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_3.cs)]  
  
 Метод доступа `get` должен завершаться инструкцией [return](../../../csharp/language-reference/keywords/return.md) или [throw](../../../csharp/language-reference/keywords/throw.md), при этом управление не может передаваться из тела метода доступа.  
  
 Изменение состояния объекта с помощью метода доступа `get` считается ошибочным стилем программирования. Например, побочным эффектом следующего метода доступа является изменение состояния объекта каждый раз при доступе к полю `number`.  
  
 [!code-csharp[csProgGuideProperties#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_4.cs)]  
  
 Метод доступа `get` можно использовать для возврата значения поля напрямую или после вычисления. Пример:  
  
 [!code-csharp[csProgGuideProperties#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_5.cs)]  
  
 Если в предыдущем фрагменте кода свойству `Name` не присвоено значение, будет возвращено значение "Нет данных".  
  
## <a name="the-set-accessor"></a>Метод доступа set  
 Метод доступа `set` похож на метод с типом возвращаемого значения [void](../../../csharp/language-reference/keywords/void.md). В нем используется неявный параметр `value`, тип которого соответствует типу свойства. В следующем примере метод доступа `set` добавляется к свойству `Name`:  
  
 [!code-csharp[csProgGuideProperties#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_6.cs)]  
  
 При присвоении значения свойству вызывается метод доступа `set` с аргументом, содержащим новое значение. Пример:  
  
 [!code-csharp[csProgGuideProperties#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_7.cs)]  
  
 Использование имени явного параметра (`value`) для объявления локальной переменной в методе доступа `set` является ошибкой.  
  
## <a name="remarks"></a>Примечания  
 Свойства могут быть помечены как `public`, `private`, `protected`, `internal`, `protected internal` или `private protected`. Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к свойству. Методы доступа `get` и `set` для одного свойства могут иметь разные модификаторы доступа. Например, метод доступа `get` может иметь модификатор `public`, разрешающий доступ из-за пределов типа только для чтения, а метод доступа `set` — модификатор `private` или `protected`. Дополнительные сведения см. в статье [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Свойство может быть объявлено как статическое с помощью ключевого слова `static`. Это делает свойство доступным для вызывающих объектов в любое время, даже если экземпляр класса не существует. Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Свойство может быть помечено как виртуальное с помощью ключевого слова [virtual](../../../csharp/language-reference/keywords/virtual.md). Это позволяет производным классам переопределять поведение свойства с помощью ключевого слова [override](../../../csharp/language-reference/keywords/override.md). Дополнительные сведения об этих параметрах см. в разделе [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md).  
  
 Свойство, переопределяющее виртуальное свойство, также может быть запечатанным ([sealed](../../../csharp/language-reference/keywords/sealed.md)). Это указывает, что для производных классов оно больше не является виртуальным. Наконец, свойство можно объявить абстрактным ([abstract](../../../csharp/language-reference/keywords/abstract.md)). Это означает, что в классе не будет определена реализация такого свойства, и в производных классах должны использоваться собственные реализации. Дополнительные сведения об этих параметрах см. в разделе [Абстрактные и запечатанные классы и члены классов](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
> [!NOTE]
>  Использование модификаторов [virtual](../../../csharp/language-reference/keywords/virtual.md), [abstract](../../../csharp/language-reference/keywords/abstract.md) или [override](../../../csharp/language-reference/keywords/override.md) в методе доступа статического ([static](../../../csharp/language-reference/keywords/static.md)) свойства является ошибкой.  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируются свойства экземпляра, а также статические и доступные только для чтения свойства. Этот метод принимает введенное с клавиатуры имя сотрудника, увеличивает значение `NumberOfEmployees` на 1, после чего отображает имя и номер сотрудника.  
  
 [!code-csharp[csProgGuideProperties#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_8.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере демонстрируется доступ к свойству базового класса, которое скрыто в производном классе другим свойством с таким же именем.  
  
 [!code-csharp[csProgGuideProperties#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_9.cs)]  
  
 На что следует обратить внимание в предыдущем примере:  
  
-   Свойство `Name` в производном классе скрывает свойство `Name` базового класса. В таком случае в объявлении свойства в производном классе используется модификатор `new`:  
  
     [!code-csharp[csProgGuideProperties#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_10.cs)]  
  
-   Для доступа к скрытому свойству в базовом классе используется приведение `(Employee)`:  
  
     [!code-csharp[csProgGuideProperties#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_11.cs)]  
  
     Дополнительные сведения о скрытии элементов см. в разделе [Модификатор new](../../../csharp/language-reference/keywords/new-modifier.md).  
  
## <a name="example"></a>Пример  
 В этом примере два класса (`Cube` и `Square`) реализуют абстрактный класс `Shape` и переопределяют его абстрактное свойство `Area`. Обратите внимание на использование модификатора [override](../../../csharp/language-reference/keywords/override.md) в свойствах. Программа принимает введенную длину стороны, на основании которой рассчитывает площади квадрата и куба. Также принимается введенное значение площади, на основании которой рассчитываются длины сторон квадрата и куба.  
  
 [!code-csharp[csProgGuideProperties#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-properties_12.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Свойства интерфейса](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
 [Автоматически реализуемые свойства](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)
