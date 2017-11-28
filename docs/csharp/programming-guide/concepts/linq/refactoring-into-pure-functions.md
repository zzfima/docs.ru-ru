---
title: "Рефакторинг в чистые функции (C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 36bb31975523055962fa9572109dab7e2ed47336
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="refactoring-into-pure-functions-c"></a>Рефакторинг в чистые функции (C#)

Важным аспектом чисто функциональных преобразований является освоение способов оптимизации существующего кода для получения чистых функций.  
  
> [!NOTE]
>  Общим подходом к функциональному программированию является оптимизация кода программ для получения чистых функций. В Visual Basic и C++ это равносильно использованию функций. Но в C# функции называются методами. В данном случае чистая функция в C# реализуется как метод.  
  
 Как отмечалось ранее в этом разделе, чистые функции имеют две полезные характеристики.  
  
-   У них отсутствуют побочные эффекты. Функции не изменяют значения или данные любого типа, не входящие в область их определения.  
  
-   Функции действуют единообразно. После получения того же набора входных данных они всегда возвращают одно и то же выходное значение.  
  
 Одним из способов перехода к функциональному программированию является оптимизация существующего кода с целью устранения ненужных побочных эффектов и внешних зависимостей. Таким образом, из существующего кода создаются чистые функции.  
  
 В этом разделе объясняется, что представляет собой чистая функция и чем она не является. В разделе [Учебник. Управление содержимым в документе WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) показано управление документом WordprocessingML и содержатся два примера рефакторинга с помощью чистых функций.  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a>Устранение побочных эффектов и внешних зависимостей  
 В следующих примерах сравниваются обычные и чистые функции.  
  
### <a name="non-pure-function-that-changes-a-class-member"></a>Обычная функция, изменяющая член класса  
 В следующем примере кода функция `HypenatedConcat` представляет собой обычную функцию, поскольку изменяет элемент данных `aMember` в классе.  
  
```csharp  
public class Program  
{  
    private static string aMember = "StringOne";  
  
    public static void HypenatedConcat(string appendStr)  
    {  
        aMember += '-' + appendStr;  
    }  
  
    public static void Main()  
    {  
        HypenatedConcat("StringTwo");  
        Console.WriteLine(aMember);  
    }  
}  
```  
  
 Этот код выводит следующие результаты:  
  
```  
StringOne-StringTwo  
```  
  
 Обратите внимание, что неважно, какой доступ имеют изменяемые данные, `public` или `private`, и являются ли они членом класса `static` или элементом экземпляра. Чистая функция не изменяет не относящиеся к ней данные.  
  
### <a name="non-pure-function-that-changes-an-argument"></a>Обычная функция, изменяющая аргумент  
 Более того, следующая версия той же функции представляет собой обычную функцию, поскольку изменяет содержимое своего параметра `sb`.  
  
```csharp  
public class Program  
{  
    public static void HypenatedConcat(StringBuilder sb, String appendStr)  
    {  
        sb.Append('-' + appendStr);  
    }  
  
    public static void Main()  
    {  
        StringBuilder sb1 = new StringBuilder("StringOne");  
        HypenatedConcat(sb1, "StringTwo");  
        Console.WriteLine(sb1);  
    }  
}  
```  
  
 Эта версия программы дает те же выходные данные, что и первая версия, поскольку функция `HypenatedConcat` изменила значение (состояние) своего первого параметра, вызвав функцию-член <xref:System.Text.StringBuilder.Append%2A>. Обратите внимание, что это изменение происходит несмотря на то, что функция `HypenatedConcat` использует передачу параметра по значению.  
  
> [!IMPORTANT]
>  Передача параметров по значению для ссылочных типов приводит к созданию копии ссылки на передаваемый объект. Эта копия все еще связана с теми же данными экземпляра, что и первоначальная ссылка (пока ссылочная переменная не будет присвоена новому объекту). Вызов по значению необязательно требуется функции для изменения параметра.  
  
### <a name="pure-function"></a>Чистая функция  
Следующая версия этой программы реализует функцию `HypenatedConcat` в виде чистой функции.  
  
```csharp  
class Program  
{  
    public static string HyphenatedConcat(string s, string appendStr)  
    {  
        return (s + '-' + appendStr);  
    }  
  
    public static void Main(string[] args)  
    {  
        string s1 = "StringOne";  
        string s2 = HyphenatedConcat(s1, "StringTwo");  
        Console.WriteLine(s2);  
    }  
}  
```  
  
 И снова она дает ту же строку вывода: `StringOne-StringTwo`. Обратите внимание, что для сохранения соединенного значения оно сохраняется в промежуточной переменной `s2`.  
  
 Одним из полезных подходов является написание функций, которые локально являются обычными (то есть в них объявляются и изменяются локальные переменные), но глобально остаются чистыми. Такие функции имеют многие характеристики, благоприятные с точки зрения компоновки, но позволяют обойтись без использования некоторых более сложных средств функционального программирования, тех, что диктуют, например, необходимость использовать рекурсию, невзирая на возможность добиться того же результата с помощью простого цикла.  
  
## <a name="standard-query-operators"></a>Стандартные операторы запроса  
 Важной характеристикой стандартных операторов запросов является то, что они реализуются как чистые функции.  
  
 Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>См. также  
 [Введение в чистые функциональные преобразования (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [Сравнение функционального и императивного программирования (C#)](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
