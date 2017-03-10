---
title: "internal (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "internal_CSharpKeyword"
  - "internal"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "internal - ключевое слово [C#]"
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# internal (Справочник по C#)
Ключевое слово `internal`[модификатор доступа](../../../csharp/language-reference/keywords/access-modifiers.md) для типов и членов типов.  Внутренние типы или члены доступны только внутри файлов в одной и той же сборке \(см. следующий пример\).  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 Доступ к типам или членам с модификатором доступа `protected internal` может осуществляться из текущей сборки или из типов, которые являются производными от содержащего их класса.  
  
 Сравнение модификатора `internal` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Дополнительные сведения о сборках см. в разделе [Сборки и глобальный кэш сборок](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
 Внутренний доступ чаще всего используется в разработке на основе компонентов, так как он позволяет группе компонентов взаимодействовать в закрытой форме, не открывая доступ остальной части кода приложения.  Например, структура для построения графических пользовательских интерфейсов может предоставлять классы `Control` и `Form`, взаимодействующие при помощи членов с внутренним доступом.  Так как эти члены являются закрытыми, они не предоставляются коду, использующему структуру.  
  
 Создание ссылки на тип или член с внутренним доступом за пределами сборки, в которой он был определен, приведет к ошибке.  
  
## Пример  
 В этом примере содержится два файла: `Assembly1.cs` и `Assembly1`\_`a.cs`.  Первый файл содержит внутренний базовый класс `BaseClass`.  Попытка создания экземпляра `BaseClass` во втором файле приведет к ошибке.  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## Пример  
 В этом примере используются те же файлы, что и в примере 1, но уровень доступности `BaseClass` изменен на `public`.  Кроме того, уровень доступности члена `IntM` изменен на `internal`.  В этом случае можно создать экземпляр класса, но доступ к внутреннему члену отсутствует.  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [защищенные](../../../csharp/language-reference/keywords/protected.md)