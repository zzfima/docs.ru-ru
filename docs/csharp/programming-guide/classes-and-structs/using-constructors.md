---
title: Руководство по программированию на C#. Использование конструкторов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 1924e218f151a86b0524df6f3c91bdbe78131922
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236171"
---
# <a name="using-constructors-c-programming-guide"></a>Использование конструкторов (Руководство по программированию на C#)
Каждый раз, когда создается [класс](../../../csharp/language-reference/keywords/class.md) или [структура](../../../csharp/language-reference/keywords/struct.md), вызывается конструктор. Конструкторы имеют имя, совпадающее с именем класса или структуры, и обычно инициализируют члены данных нового объекта.  
  
 В следующем примере класс с именем `Taxi` определяется с помощью простого конструктора. Затем оператор [new](../../../csharp/language-reference/keywords/new.md) создает экземпляр этого класса. Конструктор `Taxi` вызывается оператором `new` сразу после того, как новому объекту будет выделена память.  
  
 [!code-csharp[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 Конструктор, который не принимает никаких параметров, называется *конструктором по умолчанию*. Конструкторы по умолчанию вызываются всякий раз, когда создается экземпляр объекта с помощью оператора `new`, а аргументы в `new` не передаются. Дополнительные сведения см. в разделе [Конструкторы экземпляров](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).  
  
 Если класс является [статическим](../../../csharp/language-reference/keywords/static.md), компилятор C# выделяет классам без конструкторов открытый конструктор по умолчанию, позволяющий создавать экземпляры классов. Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Создание экземпляров класса можно запретить, сделав конструктор закрытым, следующим образом:  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 Дополнительные сведения см. в разделе [Закрытые конструкторы](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).  
  
 Конструкторы для типов [struct](../../../csharp/language-reference/keywords/struct.md) похожи на конструкторы классов, однако `structs` не может содержать явный конструктор по умолчанию, поскольку предоставляется компилятором автоматически. Этот конструктор инициализирует каждое поле в `struct` со значением по умолчанию. Дополнительные сведения см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md). При этом конструктор по умолчанию вызывается только в том случае, если `struct` создается с помощью переменной `new`. Например, в этом коде конструктор по умолчанию используется для <xref:System.Int32> — это обеспечивает инициализацию целого числа:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 В то же время следующий код вызывает ошибку компилятора, поскольку не использует `new`, и потому, что использует не инициализированный объект:  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 Кроме того, объекты на основе `structs` (включая все встроенные числовые типы) можно инициализировать или назначить, а затем использовать, как в следующем примере:  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 В связи с этим вызывать конструктор по умолчанию для типа значения необязательно.  
  
 Оба класса и `structs` могут определять конструкторы, принимающие параметры. Конструкторы, принимающие параметры, необходимо вызывать с помощью оператора `new` или [base](../../../csharp/language-reference/keywords/base.md). Классы и `structs` могут определять также несколько конструкторов; для определения конструктора по умолчанию ни один их них не требуется. Например:  
  
 [!code-csharp[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 Этот класс можно создать, воспользовавшись одним из следующих операторов:  
  
 [!code-csharp[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 Конструктор может использовать ключевое слово `base` для вызова конструктора базового класса. Например:  
  
 [!code-csharp[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 В этом примере конструктор базового класса вызывается перед выполнением соответствующего ему блока. Ключевое слово `base` можно использовать как с параметрами, так и без них. Любые параметры для конструктора можно использовать как параметры для `base` или как часть выражения. Дополнительные сведения см. в разделе [base](../../../csharp/language-reference/keywords/base.md).  
  
 В производном классе, если конструктор базового класса не вызывается явным образом с помощью ключевого слова `base`, конструктор по умолчанию, если он существует, вызывается неявно. Это означает, что следующие объявления конструкторов действуют одинаково:  
  
 [!code-csharp[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-csharp[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 Если базовый класс не предлагает конструктор по умолчанию, производный класс должен явно вызвать конструктор базового класса с помощью `base`.  
  
 Конструктор может вызывать другой конструктор в том же объекте с помощью ключевого слова [this](../../../csharp/language-reference/keywords/this.md). Как и `base`, `this` можно использовать с параметрами или без, а все параметры в конструкторе доступны как параметры `this` или как часть выражения. Например, второй конструктор в предыдущем примере можно переписать, используя `this`:   
  
 [!code-csharp[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 Применение ключевого слова `this` в приведенном выше примере привело к вызову конструктора:  
  
 [!code-csharp[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 Конструкторы могут иметь пометку [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) или [private protected](../../../csharp/language-reference/keywords/private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут создавать класс. Дополнительные сведения см. в статье [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Конструктор можно объявить статическим, используя ключевое слово [static](../../../csharp/language-reference/keywords/static.md). Статические конструкторы вызываются автоматически непосредственно перед доступом к статическим полям и обычно используются для инициализации членов статического класса. Дополнительные сведения см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделах [Конструкторы экземпляров](~/_csharplang/spec/classes.md#instance-constructors) и [Статические конструкторы](~/_csharplang/spec/classes.md#static-constructors) в [Спецификации языка C#](../../language-reference/language-specification/index.md). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)
