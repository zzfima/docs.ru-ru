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
# <a name="refactoring-into-pure-functions-c"></a><span data-ttu-id="aa2cd-102">Рефакторинг в чистые функции (C#)</span><span class="sxs-lookup"><span data-stu-id="aa2cd-102">Refactoring Into Pure Functions (C#)</span></span>

<span data-ttu-id="aa2cd-103">Важным аспектом чисто функциональных преобразований является освоение способов оптимизации существующего кода для получения чистых функций.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-103">An important aspect of pure functional transformations is learning how to refactor code using pure functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa2cd-104">Общим подходом к функциональному программированию является оптимизация кода программ для получения чистых функций.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-104">The common nomenclature in functional programming is that you refactor programs using pure functions.</span></span> <span data-ttu-id="aa2cd-105">В Visual Basic и C++ это равносильно использованию функций.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-105">In Visual Basic and C++, this aligns with the use of functions in the respective languages.</span></span> <span data-ttu-id="aa2cd-106">Но в C# функции называются методами.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-106">However, in C#, functions are called methods.</span></span> <span data-ttu-id="aa2cd-107">В данном случае чистая функция в C# реализуется как метод.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-107">For the purposes of this discussion, a pure function is implemented as a method in C#.</span></span>  
  
 <span data-ttu-id="aa2cd-108">Как отмечалось ранее в этом разделе, чистые функции имеют две полезные характеристики.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-108">As noted previously in this section, a pure function has two useful characteristics:</span></span>  
  
-   <span data-ttu-id="aa2cd-109">У них отсутствуют побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-109">It has no side effects.</span></span> <span data-ttu-id="aa2cd-110">Функции не изменяют значения или данные любого типа, не входящие в область их определения.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-110">The function does not change any variables or the data of any type outside of the function.</span></span>  
  
-   <span data-ttu-id="aa2cd-111">Функции действуют единообразно.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-111">It is consistent.</span></span> <span data-ttu-id="aa2cd-112">После получения того же набора входных данных они всегда возвращают одно и то же выходное значение.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-112">Given the same set of input data, it will always return the same output value.</span></span>  
  
 <span data-ttu-id="aa2cd-113">Одним из способов перехода к функциональному программированию является оптимизация существующего кода с целью устранения ненужных побочных эффектов и внешних зависимостей.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-113">One way of transitioning to functional programming is to refactor existing code to eliminate unnecessary side effects and external dependencies.</span></span> <span data-ttu-id="aa2cd-114">Таким образом, из существующего кода создаются чистые функции.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-114">In this way, you can create pure function versions of existing code.</span></span>  
  
 <span data-ttu-id="aa2cd-115">В этом разделе объясняется, что представляет собой чистая функция и чем она не является.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-115">This topic discusses what a pure function is and what it is not.</span></span> <span data-ttu-id="aa2cd-116">В разделе [Учебник. Управление содержимым в документе WordprocessingML (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) показано управление документом WordprocessingML и содержатся два примера рефакторинга с помощью чистых функций.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-116">The [Tutorial: Manipulating Content in a WordprocessingML Document (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial shows how to manipulate a WordprocessingML document, and includes two examples of how to refactor using a pure function.</span></span>  
  
## <a name="eliminating-side-effects-and-external-dependencies"></a><span data-ttu-id="aa2cd-117">Устранение побочных эффектов и внешних зависимостей</span><span class="sxs-lookup"><span data-stu-id="aa2cd-117">Eliminating Side Effects and External Dependencies</span></span>  
 <span data-ttu-id="aa2cd-118">В следующих примерах сравниваются обычные и чистые функции.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-118">The following examples contrast two non-pure functions and a pure function.</span></span>  
  
### <a name="non-pure-function-that-changes-a-class-member"></a><span data-ttu-id="aa2cd-119">Обычная функция, изменяющая член класса</span><span class="sxs-lookup"><span data-stu-id="aa2cd-119">Non-Pure Function that Changes a Class Member</span></span>  
 <span data-ttu-id="aa2cd-120">В следующем примере кода функция `HypenatedConcat` представляет собой обычную функцию, поскольку изменяет элемент данных `aMember` в классе.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-120">In the following code, the `HypenatedConcat` function is not a pure function, because it modifies the `aMember` data member in the class:</span></span>  
  
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
  
 <span data-ttu-id="aa2cd-121">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="aa2cd-121">This code produces the following output:</span></span>  
  
```  
StringOne-StringTwo  
```  
  
 <span data-ttu-id="aa2cd-122">Обратите внимание, что неважно, какой доступ имеют изменяемые данные, `public` или `private`, и являются ли они членом класса `static` или элементом экземпляра.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-122">Note that it is irrelevant whether the data being modified has `public` or `private` access, or is a `static` member or an instance member.</span></span> <span data-ttu-id="aa2cd-123">Чистая функция не изменяет не относящиеся к ней данные.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-123">A pure function does not change any data outside of the function.</span></span>  
  
### <a name="non-pure-function-that-changes-an-argument"></a><span data-ttu-id="aa2cd-124">Обычная функция, изменяющая аргумент</span><span class="sxs-lookup"><span data-stu-id="aa2cd-124">Non-Pure Function that Changes an Argument</span></span>  
 <span data-ttu-id="aa2cd-125">Более того, следующая версия той же функции представляет собой обычную функцию, поскольку изменяет содержимое своего параметра `sb`.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-125">Furthermore, the following version of this same function is not pure because it modifies the contents of its parameter, `sb`.</span></span>  
  
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
  
 <span data-ttu-id="aa2cd-126">Эта версия программы дает те же выходные данные, что и первая версия, поскольку функция `HypenatedConcat` изменила значение (состояние) своего первого параметра, вызвав функцию-член <xref:System.Text.StringBuilder.Append%2A>.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-126">This version of the program produces the same output as the first version, because the `HypenatedConcat` function has changed the value (state) of its first parameter by invoking the <xref:System.Text.StringBuilder.Append%2A> member function.</span></span> <span data-ttu-id="aa2cd-127">Обратите внимание, что это изменение происходит несмотря на то, что функция `HypenatedConcat` использует передачу параметра по значению.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-127">Note that this alteration occurs despite that fact that `HypenatedConcat` uses call-by-value parameter passing.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa2cd-128">Передача параметров по значению для ссылочных типов приводит к созданию копии ссылки на передаваемый объект.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-128">For reference types, if you pass a parameter by value, it results in a copy of the reference to an object being passed.</span></span> <span data-ttu-id="aa2cd-129">Эта копия все еще связана с теми же данными экземпляра, что и первоначальная ссылка (пока ссылочная переменная не будет присвоена новому объекту).</span><span class="sxs-lookup"><span data-stu-id="aa2cd-129">This copy is still associated with the same instance data as the original reference (until the reference variable is assigned to a new object).</span></span> <span data-ttu-id="aa2cd-130">Вызов по значению необязательно требуется функции для изменения параметра.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-130">Call-by-reference is not necessarily required for a function to modify a parameter.</span></span>  
  
### <a name="pure-function"></a><span data-ttu-id="aa2cd-131">Чистая функция</span><span class="sxs-lookup"><span data-stu-id="aa2cd-131">Pure Function</span></span>  
<span data-ttu-id="aa2cd-132">Следующая версия этой программы реализует функцию `HypenatedConcat` в виде чистой функции.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-132">This next version of the program shows how to implement the `HypenatedConcat` function as a pure function.</span></span>  
  
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
  
 <span data-ttu-id="aa2cd-133">И снова она дает ту же строку вывода: `StringOne-StringTwo`.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-133">Again, this version produces the same line of output: `StringOne-StringTwo`.</span></span> <span data-ttu-id="aa2cd-134">Обратите внимание, что для сохранения соединенного значения оно сохраняется в промежуточной переменной `s2`.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-134">Note that to retain the concatenated value, it is stored in the intermediate variable `s2`.</span></span>  
  
 <span data-ttu-id="aa2cd-135">Одним из полезных подходов является написание функций, которые локально являются обычными (то есть в них объявляются и изменяются локальные переменные), но глобально остаются чистыми.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-135">One approach that can be very useful is to write functions that are locally impure (that is, they declare and modify local variables) but are globally pure.</span></span> <span data-ttu-id="aa2cd-136">Такие функции имеют многие характеристики, благоприятные с точки зрения компоновки, но позволяют обойтись без использования некоторых более сложных средств функционального программирования, тех, что диктуют, например, необходимость использовать рекурсию, невзирая на возможность добиться того же результата с помощью простого цикла.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-136">Such functions have many of the desirable composability characteristics, but avoid some of the more convoluted functional programming idioms, such as having to use recursion when a simple loop would accomplish the same thing.</span></span>  
  
## <a name="standard-query-operators"></a><span data-ttu-id="aa2cd-137">Стандартные операторы запроса</span><span class="sxs-lookup"><span data-stu-id="aa2cd-137">Standard Query Operators</span></span>  
 <span data-ttu-id="aa2cd-138">Важной характеристикой стандартных операторов запросов является то, что они реализуются как чистые функции.</span><span class="sxs-lookup"><span data-stu-id="aa2cd-138">An important characteristic of the standard query operators is that they are implemented as pure functions.</span></span>  
  
 <span data-ttu-id="aa2cd-139">Дополнительные сведения см. в разделе [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="aa2cd-139">For more information, see [Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2cd-140">См. также</span><span class="sxs-lookup"><span data-stu-id="aa2cd-140">See Also</span></span>  
 [<span data-ttu-id="aa2cd-141">Введение в чистые функциональные преобразования (C#)</span><span class="sxs-lookup"><span data-stu-id="aa2cd-141">Introduction to Pure Functional Transformations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [<span data-ttu-id="aa2cd-142">Сравнение функционального и императивного программирования (C#)</span><span class="sxs-lookup"><span data-stu-id="aa2cd-142">Functional Programming vs. Imperative Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-programming-vs-imperative-programming.md)
