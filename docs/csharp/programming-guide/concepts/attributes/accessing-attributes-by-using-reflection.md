---
title: Обращение к атрибутам с помощью отражения (C#)
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: 05c051490dab5265309fd067dfb67f0ef7822541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="60bb9-102">Обращение к атрибутам с помощью отражения (C#)</span><span class="sxs-lookup"><span data-stu-id="60bb9-102">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="60bb9-103">Возможность определения настраиваемых атрибутов и их помещения в собственный исходный код не будет настолько значимой без наличия способа извлечения этих сведений и работы с ними.</span><span class="sxs-lookup"><span data-stu-id="60bb9-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="60bb9-104">Отражение позволяет извлекать сведения, определенные с настраиваемыми атрибутами.</span><span class="sxs-lookup"><span data-stu-id="60bb9-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="60bb9-105">Основным методом выступает `GetCustomAttributes`, который возвращает массив объектов, являющихся эквивалентами времени выполнения атрибутов исходного кода.</span><span class="sxs-lookup"><span data-stu-id="60bb9-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="60bb9-106">Для этого метода существует несколько перегруженных версий.</span><span class="sxs-lookup"><span data-stu-id="60bb9-106">This method has several overloaded versions.</span></span> <span data-ttu-id="60bb9-107">Дополнительные сведения см. в разделе <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="60bb9-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="60bb9-108">Спецификация атрибута, например:</span><span class="sxs-lookup"><span data-stu-id="60bb9-108">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="60bb9-109">концептуально эквивалентна следующему коду:</span><span class="sxs-lookup"><span data-stu-id="60bb9-109">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="60bb9-110">Однако код не выполняется до тех пор, пока у `SampleClass` не будут запрошены атрибуты.</span><span class="sxs-lookup"><span data-stu-id="60bb9-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="60bb9-111">Вызов `GetCustomAttributes` в `SampleClass` приведет к тому, что объект `Author` будет создан и инициализирован так, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="60bb9-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="60bb9-112">Если класс имеет другие атрибуты, другие объекты атрибутов создаются аналогично.</span><span class="sxs-lookup"><span data-stu-id="60bb9-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="60bb9-113">`GetCustomAttributes` затем возвращает объект `Author` и все другие объекты атрибутов в массиве.</span><span class="sxs-lookup"><span data-stu-id="60bb9-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="60bb9-114">Потом можно пройти по этому массиву, определить в зависимости от типа каждого элемента массива какие атрибуты были применены и извлечь сведения из объектов атрибутов.</span><span class="sxs-lookup"><span data-stu-id="60bb9-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60bb9-115">Пример</span><span class="sxs-lookup"><span data-stu-id="60bb9-115">Example</span></span>  
 <span data-ttu-id="60bb9-116">Ниже приведен полный пример.</span><span class="sxs-lookup"><span data-stu-id="60bb9-116">Here is a complete example.</span></span> <span data-ttu-id="60bb9-117">Определяется настраиваемый атрибут, который применяется к нескольким сущностям и извлекается через отражение.</span><span class="sxs-lookup"><span data-stu-id="60bb9-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="60bb9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="60bb9-118">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="60bb9-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="60bb9-119">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="60bb9-120">Извлечение информации, сохраненной в атрибуте</span><span class="sxs-lookup"><span data-stu-id="60bb9-120">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)  
 <span data-ttu-id="60bb9-121">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) (Отражение (C#))</span><span class="sxs-lookup"><span data-stu-id="60bb9-121">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md)</span></span>  
 [<span data-ttu-id="60bb9-122">Атрибуты (C#)</span><span class="sxs-lookup"><span data-stu-id="60bb9-122">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="60bb9-123">Создание настраиваемых атрибутов (C#)</span><span class="sxs-lookup"><span data-stu-id="60bb9-123">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)
