---
title: "Модификатор new (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
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
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3c636d50e6c871c529104d5f2985e861f9a652b2
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="new-modifier-c-reference"></a>Модификатор new (Справочник по C#)
При использовании в качестве модификатора объявления ключевое слово `new` явным образом скрывает члены, унаследованные от базового класса. При скрытии унаследованного члена его производная версия заменяет версию базового класса. Хотя члены можно скрывать без использования модификатора `new`, в этом случае появляется предупреждение компилятора. При использовании `new` для явного скрытия члена, предупреждение не появляется.  
  
 Чтобы скрыть унаследованный член, объявите его в производном классе с использованием такого же имени члена и измените с помощью ключевого слова `new`. Пример:  
  
 [!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]  
  
 В этом примере `BaseC.Invoke` скрывается с помощью `DerivedC.Invoke`. Поле `x` не затрагивается, поскольку оно не скрыто таким же именем.  
  
 Скрытие имен через наследование принимает одну из следующих форм.  
  
-   Как правило, константы, поля, свойства и типы, которые вводятся в классе или структуре, скрывают все члены базового класса с таким же именем.  Однако существуют особые случаи.  Например, если объявить новое поле с именем `N`, чтобы сделать тип невызываемым, в то время как в базовом типе был объявлен метод `N`, новое поле не скрывает базовое объявление в синтаксисе вызова.  Подробные сведения см. в разделе [Спецификация языка C#](http://go.microsoft.com/fwlink/?LinkId=199552) (подраздел "Поиск члена" в разделе "Выражения").  
  
-   Метод, введенный в классе или структуре, скрывает свойства, поля и типы с тем же именем в базовом классе. Кроме того, он также скрывает все методы базового класса, имеющие такую же сигнатуру.  
  
-   Индексатор, представленный в классе или структуре, скрывает все индексаторы базового класса, имеющие одинаковую сигнатуру.  
  
 Совместное использование модификаторов `new` и [override](../../../csharp/language-reference/keywords/override.md) в одном члене является недопустимым, так как эти два модификатора имеют взаимоисключающие значения. Модификатор `new` создает новый член с таким же именем и приводит к скрытию исходного члена. Модификатор `override` расширяет реализацию для наследуемого члена.  
  
 При использовании модификатора `new` в объявлении, которое не скрывает наследуемый член, возникает предупреждение.  
  
## <a name="example"></a>Пример  
 В этом примере базовый класс `BaseC` и производный класс `DerivedC` используют одно и то же имя поля `x`, которое скрывает значение унаследованного поля. В примере показано использование модификатора `new`. Здесь также показано обращение к скрытым членам базового класса с помощью их полных имен.  
  
 [!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере вложенный класс скрывает класс, имеющий такое же имя в базовом классе. Здесь показано использование модификатора `new` для исключения предупреждений, а также обращение к членам скрытого класса с помощью их полных имен.  
  
 [!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]  
  
 В случае удаления модификатора `new` программа продолжит компиляцию и выполнение, однако появится следующее предупреждение.  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Управление версиями с помощью ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)   
 [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
