---
title: "Практическое руководство. Управление версиями с помощью ключевых слов &quot;Override&quot; и &quot;New&quot; (Руководство по программированию в C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# - язык, override и new"
  - "C# - язык, управление версиями"
ms.assetid: 88247d07-bd0d-49e9-a619-45ccbbfdf0c5
caps.latest.revision: 25
caps.handback.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Управление версиями с помощью ключевых слов &quot;Override&quot; и &quot;New&quot; (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Функции языка C\# позволяют обеспечить и поддерживать обратную совместимость за счет управления версиями между [базовыми](../../../csharp/language-reference/keywords/base.md) и производными классами в различных библиотеках.  Это означает, например, что если в базовом [классе](../../../csharp/language-reference/keywords/class.md) будет создан новый член, имя которого совпадает с именем члена в производном классе, язык C\# обработает такую ситуацию, и она не приведет к непредвиденным результатам.  Это также означает, что в классе должно быть явно указано, будет ли метод переопределять наследуемый метод, или это новый метод, который будет скрывать наследуемый метод с тем же именем.  
  
 В C\# производный класс может включать методы с теми же именами, что и у методов базового класса.  
  
-   Метод базового класса может быть определен как [виртуальный](../../../csharp/language-reference/keywords/virtual.md).  
  
-   Если перед методом в производном классе не указано ключевое слово [new](../../../csharp/language-reference/keywords/new.md) или [override](../../../csharp/language-reference/keywords/override.md), компилятор выдаст предупреждение, и обработка метода будет производиться как в случае наличия ключевого слова `new`.  
  
-   Если перед методом в производном классе указано ключевое слово `new`, то этот метод определен как независимый от метода в базовом классе.  
  
-   Если перед методом в производном классе указано ключевое слово `override`, то объекты производного класса будут вызывать этот метод вместо метода базового класса.  
  
-   Базовый метод можно вызвать из производного класса с помощью ключевого слова `base`.  
  
-   Ключевые слова `override`, `virtual` и `new` могут также применяться к свойствам, индексам и событиям.  
  
 По умолчанию методы в языке C\# не являются виртуальными.  Если метод объявлен как виртуальный, то любой класс, наследующий этот метод, может реализовать собственную версию.  Чтобы сделать метод виртуальным, в объявлении метода базового класса используется модификатор `virtual`.  Производный класс может переопределить базовый виртуальный метод с помощью ключевого слова `override` или скрыть виртуальный метод в базовом классе с помощью ключевого слова `new`.  Если ключевые слова `override` и `new` не указаны, компилятор выдаст предупреждение, и метод в производном классе будет скрывать метод в базовом классе.  
  
 Чтобы продемонстрировать это на практике, предположим, что компания А создала класс с именем `GraphicsClass`, используемый вашей программой.  Это класс `GraphicsClass`:  
  
 [!code-cs[csProgGuideInheritance#27](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_1.cs)]  
  
 Ваша компания использует этот класс, и вы применили его для создания собственного производного класса, добавив новый метод:  
  
 [!code-cs[csProgGuideInheritance#28](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_2.cs)]  
  
 Ваше приложение работало без проблем до тех пор, пока компания А не выпустила новую версию класса `GraphicsClass` со следующим кодом:  
  
 [!code-cs[csProgGuideInheritance#29](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_3.cs)]  
  
 Новая версия класса `GraphicsClass` теперь имеет метод с именем `DrawRectangle`.  Сначала ничего особенного не произошло.  Новая версия совместима со старой на уровне машинных кодов.  Все развернутое программное обеспечение будет продолжать работать, даже если в компьютерных системах будет установлен новый класс.  Все существующие вызовы метода `DrawRectangle` будут продолжать ссылаться на вашу версию в созданном вами производном классе.  
  
 Однако сразу после перекомпиляции приложения с помощью новой версии класса `GraphicsClass` компилятор выдаст предупреждение CS0108.  В этом предупреждении вам будет предложено принять решение относительно работы метода `DrawRectangle` в вашем приложении.  
  
 Если ваш метод должен переопределить новый метод базового класса, используйте ключевое слово `override`:  
  
 [!code-cs[csProgGuideInheritance#30](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_4.cs)]  
  
 Ключевое слово `override` заставляет все объекты, являющиеся производными от `YourDerivedGraphicsClass`, использовать версию `DrawRectangle` производного класса.  Объекты, являющиеся производными от класса `YourDerivedGraphicsClass`, могут продолжать использовать версию метода `DrawRectangle` базового класса, используя ключевое слово "base":  
  
 [!code-cs[csProgGuideInheritance#44](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_5.cs)]  
  
 Если ваш метод не должен переопределять новый метод базового класса, следуйте приведенным ниже рекомендациям.  Чтобы избежать путаницы между двумя методами, вы можете переименовать свой метод.  Это отнимает много времени и может привести к возникновению ошибок, поэтому не всегда удобно.  Однако, если ваш проект невелик, можно использовать функции оптимизации кода Visual Studio для переименования метода.  Дополнительные сведения см. в разделе [Refactoring Classes and Types \(Class Designer\)](/visual-studio/ide/refactoring-classes-and-types-class-designer).  
  
 Чтобы избежать появления предупреждения, можно также использовать ключевое слово `new` в определении производного класса:  
  
 [!code-cs[csProgGuideInheritance#31](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_6.cs)]  
  
 Использование ключевого слова `new` сообщает компилятору, что ваше определение скрывает определение, содержащееся в базовом классе.  Это поведение установлено по умолчанию.  
  
## Переопределение и выбор метода  
 При вызове метода класса компилятор C\# выбирает наилучший из методов, совместимых с вызовом \(например, если имеются два метода с одинаковыми именами\), и параметров, которые совместимы с переданным параметром.  Следующие методы будут совместимы:  
  
 [!code-cs[csProgGuideInheritance#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_7.cs)]  
  
 Если выполняется вызов `DoWork` из экземпляра `Derived`, компилятор C\# сначала попытается обеспечить совместимость вызова с версиями `DoWork`, первоначально объявленными в `Derived`.  Переназначенные методы не рассматриваются как объявленные в классе. Они являются новыми реализациями метода, объявленного в базовом классе.  Только в том случае, если компилятор C\# не смог сопоставить вызов метода с исходным методом в классе `Derived`, он попытается сопоставить вызов с переназначенным методом с тем же именем и совместимыми параметрами.  Примеры.  
  
 [!code-cs[csProgGuideInheritance#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_8.cs)]  
  
 Поскольку переменную `val` можно неявно преобразовать в тип "double", компилятор C\# вызовет `DoWork(double)` вместо `DoWork(int)`.  Чтобы избежать этого, существует два способа.  Во\-первых, избегайте объявления новых методов с одинаковыми именами в качестве виртуальных.  Во\-вторых, можно сделать так, чтобы компилятор C\# вызвал виртуальный метод, заставив его выполнить поиск в списке методов базового класса за счет приведения экземпляра `Derived` к `Base`.  Поскольку метод является виртуальным, будет вызвана реализация `DoWork(int)` в классе `Derived`.  Примеры.  
  
 [!code-cs[csProgGuideInheritance#34](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/versioning-with-the-override-and-new-keywords_9.cs)]  
  
 Дополнительные примеры см. в разделе [Использование ключевых слов Override и New](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)`new` и `override`.  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Наследование](../../../csharp/programming-guide/classes-and-structs/inheritance.md)