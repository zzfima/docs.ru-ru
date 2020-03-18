---
title: internal. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords:
- internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
ms.openlocfilehash: e5a5ca18828b689241abbb6d80c5adc51efb073c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173605"
---
# <a name="internal-c-reference"></a>internal (Справочник по C#)
Ключевое слово `internal` является [модификатором доступа](./access-modifiers.md) для типов и членов типов.
  
 > Эта страница содержит доступ `internal`. Ключевое слово `internal` также является частью модификатора доступа [`protected internal`](./protected-internal.md).
  
Внутренние типы или члены доступны только внутри файлов в той же сборке, как в следующем примере:  
  
```csharp  
public class BaseClass
{  
    // Only accessible within the same assembly.
    internal static int x = 0;
}  
```  

 Сравнение модификатора `internal` с другими модификаторами доступа см. в разделах [Уровни доступности](./accessibility-levels.md) и [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).  
  
 См. дополнительные сведения о [сборках в .NET](../../../standard/assembly/index.md).  
  
 Обычно доступ к внутренним компонентам используется в разработке на основе компонентов, так как он позволяет группе компонентов взаимодействовать в закрытой форме, без их предоставления остальной части кода приложения. Например, платформа для создания графических интерфейсов пользователя может предоставлять классы `Control` и `Form`, взаимодействующие с помощью членов с внутренним доступом. Поскольку эти члены являются внутренними, они не предоставляются коду, использующему платформу.  
  
 Будет ошибкой ссылаться на тип или член с внутренним доступом из-за пределов сборки, в которой он определен.  
  
## <a name="example"></a>Пример  
 Этот пример содержит два файла, `Assembly1.cs` и `Assembly1_a.cs`. Первый файл содержит внутренний базовый класс `BaseClass`. Во втором файле попытка создать экземпляр `BaseClass` приведет к ошибке.  
  
```csharp  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass
{  
   public static int intM = 0;  
}  
```  
  
```csharp  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a>Пример  
 В этом примере используйте те же файлы, которые использовались в примере 1, однако измените уровень доступности `BaseClass` на `public`. Кроме того, измените уровень доступности члена `intM` на `internal`. В этом случае можно создать экземпляр класса, но нельзя получить доступ к внутреннему члену.  
  
```csharp  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass
{  
   internal static int intM = 0;  
}  
```  
  
```csharp  
// Assembly2_a.cs  
// Compile with: /reference:Assembly2.dll  
public class TestAccess
{  
   static void Main()
   {  
      var myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Объявленная доступность](~/_csharplang/spec/basic-concepts.md#declared-accessibility) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [Модификаторы доступа](./access-modifiers.md)
- [Уровни доступности](./accessibility-levels.md)
- [Модификаторы](index.md)
- [public](./public.md)
- [private](./private.md)
- [protected](./protected.md)
