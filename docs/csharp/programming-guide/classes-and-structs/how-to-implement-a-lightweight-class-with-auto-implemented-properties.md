---
title: Практическое руководство. Реализация упрощенного класса с автоматически реализуемыми свойствами - руководство по программированию на C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: a987d0501e36232993a2f1a2b4ebda29d007afd0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618650"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="9ab8d-102">Практическое руководство. Реализация упрощенного класса с автоматически реализуемыми свойствами (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9ab8d-102">How to: Implement a Lightweight Class with Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="9ab8d-103">В этом примере показано, как создать неизменяемый упрощенный класс, служащий исключительно для инкапсуляции набора автоматически реализуемых свойств.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-103">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="9ab8d-104">Используйте такую конструкцию вместо структуры, когда требуется использовать семантику ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-104">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>  
  
 <span data-ttu-id="9ab8d-105">Неизменяемое свойство можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-105">You can make an immutable property in two ways.</span></span>  <span data-ttu-id="9ab8d-106">Можно объявить метод доступа [set](../../../csharp/language-reference/keywords/set.md) как [private](../../../csharp/language-reference/keywords/private.md).</span><span class="sxs-lookup"><span data-stu-id="9ab8d-106">You can declare the [set](../../../csharp/language-reference/keywords/set.md) accessor to be [private](../../../csharp/language-reference/keywords/private.md).</span></span>  <span data-ttu-id="9ab8d-107">Свойство можно задать только в типе, но оно является неизменяемым для потребителей.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-107">The property is only settable within the type, but it is immutable to consumers.</span></span>  <span data-ttu-id="9ab8d-108">Вместо этого можно объявить только метод доступа [get](../../../csharp/language-reference/keywords/get.md), который делает свойство неизменяемым везде, кроме конструктора типа.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-108">You can instead declare only the [get](../../../csharp/language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type’s constructor.</span></span>  
  
 <span data-ttu-id="9ab8d-109">При объявлении закрытого метода доступа `set` для инициализации свойства нельзя использовать инициализатор объекта.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-109">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="9ab8d-110">Необходимо использовать конструктор или фабричный метод.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-110">You must use a constructor or a factory method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ab8d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="9ab8d-111">Example</span></span>  
 <span data-ttu-id="9ab8d-112">В следующем примере показаны два способа реализации неизменяемого класса с автоматически реализуемыми свойствами.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-112">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="9ab8d-113">Каждый способ объявляет одно из свойств с закрытым методом доступа `set` и одно из свойств только с методом доступа `get`.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-113">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="9ab8d-114">Первый класс использует конструктор только для инициализации свойства, а второй класс использует статический фабричный метод, вызывающий конструктор.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-114">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>  
  
```csharp  
// This class is immutable. After an object is created,   
    // it cannot be modified from outside the class. It uses a   
    // constructor to initialize its properties.   
    class Contact  
    {  
        // Read-only properties.   
        public string Name { get; }  
        public string Address { get; private set; }  
  
        // Public constructor.   
        public Contact(string contactName, string contactAddress)  
        {  
            Name = contactName;  
            Address = contactAddress;                 
        }  
    }  
  
    // This class is immutable. After an object is created,   
    // it cannot be modified from outside the class. It uses a   
    // static method and private constructor to initialize its properties.      
    public class Contact2  
    {  
        // Read-only properties.   
        public string Name { get; private set; }  
        public string Address { get; }  
  
        // Private constructor.   
        private Contact2(string contactName, string contactAddress)  
        {  
            Name = contactName;  
            Address = contactAddress;                 
        }  
  
        // Public factory method.   
        public static Contact2 CreateContact(string name, string address)  
        {  
            return new Contact2(name, address);  
        }  
    }  
  
    public class Program  
    {   
        static void Main()  
        {  
            // Some simple data sources.   
            string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",   
                              "Cesar Garcia", "Debra Garcia"};  
            string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",  
                                  "12 108th St.", "89 E. 42nd St."};  
  
            // Simple query to demonstrate object creation in select clause.   
            // Create Contact objects by using a constructor.   
            var query1 = from i in Enumerable.Range(0, 5)  
                        select new Contact(names[i], addresses[i]);  
  
            // List elements cannot be modified by client code.   
            var list = query1.ToList();  
            foreach (var contact in list)  
            {  
                Console.WriteLine("{0}, {1}", contact.Name, contact.Address);  
            }  
  
            // Create Contact2 objects by using a static factory method.   
            var query2 = from i in Enumerable.Range(0, 5)  
                         select Contact2.CreateContact(names[i], addresses[i]);  
  
            // Console output is identical to query1.   
            var list2 = query2.ToList();  
  
            // List elements cannot be modified by client code.   
            // CS0272:   
            // list2[0].Name = "Eugene Zabokritski";   
  
            // Keep the console open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();                  
        }  
    }  
  
/* Output:  
    Terry Adams, 123 Main St.  
    Fadi Fakhouri, 345 Cypress Ave.  
    Hanying Feng, 678 1st Ave  
    Cesar Garcia, 12 108th St.  
    Debra Garcia, 89 E. 42nd St.  
*/  
```  
  
 <span data-ttu-id="9ab8d-115">Компилятор создает резервные поля для каждого автоматически реализуемого свойства.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-115">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="9ab8d-116">Эти поля недоступны непосредственно из исходного кода.</span><span class="sxs-lookup"><span data-stu-id="9ab8d-116">The fields are not accessible directly from source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ab8d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9ab8d-117">See also</span></span>

- [<span data-ttu-id="9ab8d-118">Свойства</span><span class="sxs-lookup"><span data-stu-id="9ab8d-118">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="9ab8d-119">struct</span><span class="sxs-lookup"><span data-stu-id="9ab8d-119">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)
- [<span data-ttu-id="9ab8d-120">Инициализаторы объектов и коллекций</span><span class="sxs-lookup"><span data-stu-id="9ab8d-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
