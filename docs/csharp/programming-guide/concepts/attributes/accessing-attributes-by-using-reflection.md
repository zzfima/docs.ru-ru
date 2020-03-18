---
title: Обращение к атрибутам с помощью отражения (C#)
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: 990b6487e50bfb2d123c3871e5f85da063711d9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595503"
---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="86aff-102">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="86aff-102">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="86aff-103">Возможность определения настраиваемых атрибутов и их помещения в собственный исходный код не будет настолько значимой без наличия способа извлечения этих сведений и работы с ними.</span><span class="sxs-lookup"><span data-stu-id="86aff-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="86aff-104">Отражение позволяет извлекать сведения, определенные с настраиваемыми атрибутами.</span><span class="sxs-lookup"><span data-stu-id="86aff-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="86aff-105">Основным методом выступает `GetCustomAttributes`, который возвращает массив объектов, являющихся эквивалентами времени выполнения атрибутов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="86aff-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="86aff-106">Для этого метода существует несколько перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="86aff-106">This method has several overloaded versions.</span></span> <span data-ttu-id="86aff-107">Дополнительные сведения см. в разделе <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="86aff-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="86aff-108">Спецификация атрибута, например:</span><span class="sxs-lookup"><span data-stu-id="86aff-108">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="86aff-109">концептуально эквивалентна следующему коду:</span><span class="sxs-lookup"><span data-stu-id="86aff-109">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="86aff-110">Однако код не выполняется до тех пор, пока у `SampleClass` не будут запрошены атрибуты.</span><span class="sxs-lookup"><span data-stu-id="86aff-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="86aff-111">Вызов `GetCustomAttributes` в `SampleClass` приведет к тому, что объект `Author` будет создан и инициализирован так, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="86aff-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="86aff-112">Если класс имеет другие атрибуты, другие объекты атрибутов создаются аналогично.</span><span class="sxs-lookup"><span data-stu-id="86aff-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="86aff-113">`GetCustomAttributes` затем возвращает объект `Author` и все другие объекты атрибутов в массиве.</span><span class="sxs-lookup"><span data-stu-id="86aff-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="86aff-114">Потом можно пройти по этому массиву, определить в зависимости от типа каждого элемента массива какие атрибуты были применены и извлечь сведения из объектов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="86aff-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86aff-115">Пример</span><span class="sxs-lookup"><span data-stu-id="86aff-115">Example</span></span>  
 <span data-ttu-id="86aff-116">Ниже приведен полный пример.</span><span class="sxs-lookup"><span data-stu-id="86aff-116">Here is a complete example.</span></span> <span data-ttu-id="86aff-117">Определяется настраиваемый атрибут, который применяется к нескольким сущностям и извлекается через отражение.</span><span class="sxs-lookup"><span data-stu-id="86aff-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="86aff-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="86aff-118">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="86aff-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="86aff-119">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="86aff-120">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="86aff-120">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="86aff-121">Отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="86aff-121">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="86aff-122">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="86aff-122">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="86aff-123">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="86aff-123">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
