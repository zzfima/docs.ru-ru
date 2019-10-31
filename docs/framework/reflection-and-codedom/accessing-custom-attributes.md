---
title: Доступ к пользовательским атрибутам
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
ms.openlocfilehash: a5651e9dc8cf40e737dd523ec5d29e876a9c0765
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130301"
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="4709d-102">Доступ к пользовательским атрибутам</span><span class="sxs-lookup"><span data-stu-id="4709d-102">Accessing Custom Attributes</span></span>
<span data-ttu-id="4709d-103">После того как с элементами программы связаны атрибуты, можно использовать отражение для проверки их существования и получения значений.</span><span class="sxs-lookup"><span data-stu-id="4709d-103">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="4709d-104">В .NET Framework версии 1.0 и 1.1 пользовательские атрибуты проверяются в контексте выполнения.</span><span class="sxs-lookup"><span data-stu-id="4709d-104">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="4709d-105">Платформа .NET Framework версии 2.0 предоставляет новый контекст загрузки — контекст только для отражения, используемый для проверки кода, который не может быть загружен для выполнения.</span><span class="sxs-lookup"><span data-stu-id="4709d-105">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="4709d-106">Контекст только для отражения</span><span class="sxs-lookup"><span data-stu-id="4709d-106">The Reflection-Only Context</span></span>  
 <span data-ttu-id="4709d-107">Код, загруженный в контекст только для отражения, не может быть выполнен.</span><span class="sxs-lookup"><span data-stu-id="4709d-107">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="4709d-108">Это означает, что экземпляры пользовательских атрибутов не могут быть созданы, потому что это потребует выполнения соответствующих конструкторов.</span><span class="sxs-lookup"><span data-stu-id="4709d-108">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="4709d-109">Чтобы загрузить и просмотреть пользовательские атрибуты в контексте только для отражения, используйте класс <xref:System.Reflection.CustomAttributeData>.</span><span class="sxs-lookup"><span data-stu-id="4709d-109">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="4709d-110">Экземпляры этого класса можно получить посредством использования допустимой перегрузки статического метода <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4709d-110">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="4709d-111">См. раздел [Практическое руководство. Загрузка сборок в контекст, предназначенный только для отражения](how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="4709d-111">See [How to: Load Assemblies into the Reflection-Only Context](how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="4709d-112">Контекст выполнения</span><span class="sxs-lookup"><span data-stu-id="4709d-112">The Execution Context</span></span>  
 <span data-ttu-id="4709d-113">Основные методы отражения, используемые для запроса атрибутов в контексте выполнения — это <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> и <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4709d-113">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="4709d-114">Возможность доступа к пользовательскому атрибуту проверяется относительно сборки, с которой он связан.</span><span class="sxs-lookup"><span data-stu-id="4709d-114">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="4709d-115">Это эквивалентно проверке того, может ли метод типа в сборке, с которой связан атрибут, вызвать конструктор этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="4709d-115">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="4709d-116">Такие методы, как <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType>, проверяют видимость и доступность аргумента типа.</span><span class="sxs-lookup"><span data-stu-id="4709d-116">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="4709d-117">Получить атрибут определенного пользователем типа с помощью метода **GetCustomAttributes** может только код в сборке, содержащей этот тип.</span><span class="sxs-lookup"><span data-stu-id="4709d-117">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="4709d-118">В следующем примере C# показан типичный способ задания пользовательского атрибута.</span><span class="sxs-lookup"><span data-stu-id="4709d-118">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="4709d-119">Этот пример иллюстрирует модель отражения пользовательских атрибутов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4709d-119">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```csharp
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="4709d-120">Если среда выполнения пытается получить пользовательские атрибуты для открытого типа пользовательского атрибута <xref:System.ComponentModel.DescriptionAttribute>, присоединенного к методу **GetLanguage**, она выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="4709d-120">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1. <span data-ttu-id="4709d-121">Среда выполнения проверяет, является ли аргумент типа **DescriptionAttribute** для метода **Type.GetCustomAttributes**(тип *type*) и, следовательно, видимым и доступным.</span><span class="sxs-lookup"><span data-stu-id="4709d-121">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2. <span data-ttu-id="4709d-122">Среда выполнения проверяет, является ли определяемый пользователем тип **MyDescriptionAttribute**, производный от **DescriptionAttribute**, видимым и доступным в сборке **System.Web.DLL**, в которой он присоединен к методу **GetLanguage**().</span><span class="sxs-lookup"><span data-stu-id="4709d-122">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3. <span data-ttu-id="4709d-123">Среда выполнения проверяет, является ли конструктор атрибута **MyDescriptionAttribute** видимым и доступным в сборке **System.Web.DLL**.</span><span class="sxs-lookup"><span data-stu-id="4709d-123">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4. <span data-ttu-id="4709d-124">Среда выполнения вызывает конструктор атрибута **MyDescriptionAttribute** с параметрами пользовательского атрибута и возвращает в вызывающий код новый объект.</span><span class="sxs-lookup"><span data-stu-id="4709d-124">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="4709d-125">Модель отражения пользовательских атрибутов может создать экземпляры определенного пользователем типа вне сборки, в которой этот тип определен.</span><span class="sxs-lookup"><span data-stu-id="4709d-125">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="4709d-126">Возникает та же ситуация, что и в случае элементов в системной библиотеке среды выполнения, которые возвращают экземпляры определяемых пользователем типов, как, например, метод <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> возвращает массив объектов **RuntimeMethodInfo**.</span><span class="sxs-lookup"><span data-stu-id="4709d-126">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="4709d-127">Чтобы клиент не смог получить сведения о типе атрибута, определенном пользователем, следует описать элементы этого типа как неоткрытые.</span><span class="sxs-lookup"><span data-stu-id="4709d-127">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="4709d-128">В следующем примере показан простейший способ использования отражения для получения доступа к пользовательским атрибутам.</span><span class="sxs-lookup"><span data-stu-id="4709d-128">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4709d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="4709d-129">See also</span></span>

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4709d-130">Просмотр сведений о типах</span><span class="sxs-lookup"><span data-stu-id="4709d-130">Viewing Type Information</span></span>](viewing-type-information.md)
- [<span data-ttu-id="4709d-131">Соображения о безопасности для отражения</span><span class="sxs-lookup"><span data-stu-id="4709d-131">Security Considerations for Reflection</span></span>](security-considerations-for-reflection.md)
