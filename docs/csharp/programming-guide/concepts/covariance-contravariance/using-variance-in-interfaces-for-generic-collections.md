---
title: Использование вариативности в интерфейсах для универсальных коллекций (C#)
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: b891ccde93e18baf5d5e814911666e9c6268e009
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169744"
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a><span data-ttu-id="90d96-102">Использование вариативности в интерфейсах для универсальных коллекций (C#)</span><span class="sxs-lookup"><span data-stu-id="90d96-102">Using Variance in Interfaces for Generic Collections (C#)</span></span>
<span data-ttu-id="90d96-103">Ковариантный интерфейс позволяет его методам возвращать более производные типы, чем указанные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="90d96-103">A covariant interface allows its methods to return more derived types than those specified in the interface.</span></span> <span data-ttu-id="90d96-104">Контравариантный интерфейс позволяет его методам принимать параметры менее производных типов, чем указанные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="90d96-104">A contravariant interface allows its methods to accept parameters of less derived types than those specified in the interface.</span></span>  
  
 <span data-ttu-id="90d96-105">В .NET Framework 4 несколько имеющихся интерфейсов стали ковариантными и контравариантными.</span><span class="sxs-lookup"><span data-stu-id="90d96-105">In .NET Framework 4, several existing interfaces became covariant and contravariant.</span></span> <span data-ttu-id="90d96-106">В их числе <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601>.</span><span class="sxs-lookup"><span data-stu-id="90d96-106">These include <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601>.</span></span> <span data-ttu-id="90d96-107">Это позволяет повторно использовать методы, оперирующие универсальными коллекциями базовых типов, для коллекций производных типов.</span><span class="sxs-lookup"><span data-stu-id="90d96-107">This enables you to reuse methods that operate with generic collections of base types for collections of derived types.</span></span>  
  
 <span data-ttu-id="90d96-108">Список вариативных интерфейсов в .NET Framework см. в разделе [Вариативность в универсальных интерфейсах (C#)](./variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="90d96-108">For a list of variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (C#)](./variance-in-generic-interfaces.md).</span></span>  
  
## <a name="converting-generic-collections"></a><span data-ttu-id="90d96-109">Преобразование универсальных коллекций</span><span class="sxs-lookup"><span data-stu-id="90d96-109">Converting Generic Collections</span></span>  
 <span data-ttu-id="90d96-110">Следующий пример иллюстрирует преимущества поддержки ковариантности в интерфейсе <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="90d96-110">The following example illustrates the benefits of covariance support in the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="90d96-111">Метод `PrintFullName` принимает коллекцию типа `IEnumerable<Person>` в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="90d96-111">The `PrintFullName` method accepts a collection of the `IEnumerable<Person>` type as a parameter.</span></span> <span data-ttu-id="90d96-112">При этом его можно повторно использовать для коллекции типа `IEnumerable<Employee>`, так как `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="90d96-112">However, you can reuse it for a collection of the `IEnumerable<Employee>` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a><span data-ttu-id="90d96-113">Сравнение универсальных коллекций</span><span class="sxs-lookup"><span data-stu-id="90d96-113">Comparing Generic Collections</span></span>  
 <span data-ttu-id="90d96-114">Следующий пример иллюстрирует преимущества поддержки контрвариантности в интерфейсе <xref:System.Collections.Generic.IComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="90d96-114">The following example illustrates the benefits of contravariance support in the <xref:System.Collections.Generic.IComparer%601> interface.</span></span> <span data-ttu-id="90d96-115">Класс `PersonComparer` реализует интерфейс `IComparer<Person>`.</span><span class="sxs-lookup"><span data-stu-id="90d96-115">The `PersonComparer` class implements the `IComparer<Person>` interface.</span></span> <span data-ttu-id="90d96-116">Тем не менее этот класс можно повторно использовать для сравнения последовательности объектов типа `Employee`, так как `Employee` наследует `Person`.</span><span class="sxs-lookup"><span data-stu-id="90d96-116">However, you can reuse this class to compare a sequence of objects of the `Employee` type because `Employee` inherits `Person`.</span></span>  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="90d96-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90d96-117">See also</span></span>

- [<span data-ttu-id="90d96-118">Вариативность в универсальных интерфейсах (C#)</span><span class="sxs-lookup"><span data-stu-id="90d96-118">Variance in Generic Interfaces (C#)</span></span>](./variance-in-generic-interfaces.md)
