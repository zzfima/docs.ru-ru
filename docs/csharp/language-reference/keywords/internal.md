---
title: "internal (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
dev_langs:
- CSharp
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: 23
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5674a78e2c317357c31d9e2661a25ce86cbf4f6a
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="internal-c-reference"></a>internal (Справочник по C#)
Ключевое слово `internal` является [модификатором доступа](../../../csharp/language-reference/keywords/access-modifiers.md) для типов и членов типов. Внутренние типы или члены доступны только внутри файлов в той же сборке, как в следующем примере:  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  
  
 Доступ к типам и членам, которые имеют модификатор доступа `protected internal`, может осуществляться из текущей сборки или типов, которые являются производными от содержащего класса.  
  
 Сравнение модификатора `internal` с другими модификаторами доступа см. в разделах [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) и [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Дополнительные сведения о сборках см. в разделе [Сборки и глобальный кэш сборок](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).  
  
 Обычно доступ к внутренним компонентам используется в разработке на основе компонентов, так как он позволяет группе компонентов взаимодействовать в закрытой форме, без их предоставления остальной части кода приложения. Например, платформа для создания графических интерфейсов пользователя может предоставлять классы `Control` и `Form`, взаимодействующие с помощью членов с внутренним доступом. Поскольку эти члены являются внутренними, они не предоставляются коду, использующему платформу.  
  
 Будет ошибкой ссылаться на тип или член с внутренним доступом из-за пределов сборки, в которой он определен.  
  
## <a name="example"></a>Пример  
 Этот пример содержит два файла, `Assembly1.cs` и `Assembly1_a.cs`. Первый файл содержит внутренний базовый класс `BaseClass`. Во втором файле попытка создать экземпляр `BaseClass` приведет к ошибке.  
  
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
  
## <a name="example"></a>Пример  
 В этом примере используйте те же файлы, которые использовались в примере 1, однако измените уровень доступности `BaseClass` на `public`. Кроме того, измените уровень доступности члена `IntM` на `internal`. В этом случае можно создать экземпляр класса, но нельзя получить доступ к внутреннему члену.  
  
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
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)

